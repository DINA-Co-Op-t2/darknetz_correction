# [darknetz/host/Makefile] - 최종 완성본

# 1. 크로스 컴파일러 (본인 경로 확인)
CC = /home/cheonsh/Linux_for_Tegra/aarch64--glibc--stable-final/bin/aarch64-buildroot-linux-gnu-gcc

# 2. OP-TEE SDK 경로 (헤더/라이브러리 찾는 곳)
OPTEE_SDK_PATH = /home/cheonsh/Linux_for_Tegra/public_sources/Linux_for_Tegra/source/public/nvidia-jetson-optee-source/optee/install/t194/usr

# 3. 실행 파일 이름
BINARY = darknetp

# 4. 헤더 경로 (SDK include 추가)
CFLAGS += -Wall -I../ta/include -I./include -I./src -I./examples
CFLAGS += -I$(OPTEE_SDK_PATH)/include

# 5. 라이브러리 경로 (SDK lib 추가)
LDFLAGS += -L$(OPTEE_SDK_PATH)/lib -lteec -lpthread -lm

# 6. 소스 파일 목록 (오타 수정됨: tcp.transfer -> tcp_transfer)
OBJSCR = src/
EXECSCR = examples/
EXECMAIN = main.o

OBJ = tcp_transfer.o diffprivate.o gemm.o utils.o cuda.o deconvolutional_layer.o convolutional_layer.o list.o image.o activations.o im2col.o col2im.o blas.o crop_layer.o dropout_layer.o maxpool_layer.o softmax_layer.o data.o matrix.o network.o connected_layer.o cost_layer.o parser.o option_list.o detection_layer.o route_layer.o upsample_layer.o box.o normalization_layer.o avgpool_layer.o layer.o local_layer.o shortcut_layer.o logistic_layer.o activation_layer.o rnn_layer.o gru_layer.o crnn_layer.o demo.o batchnorm_layer.o region_layer.o reorg_layer.o tree.o  lstm_layer.o l2norm_layer.o yolo_layer.o iseg_layer.o
EXECOBJ = captcha.o lsd.o super.o art.o tag.o cifar.o go.o rnn.o segmenter.o regressor.o classifier.o coco.o yolo.o detector.o nightmare.o instance-segmenter.o darknet.o

OBJS = $(addprefix $(OBJSCR), $(OBJ))
EXECOBJS = $(addprefix $(EXECSCR), $(EXECOBJ))

.PHONY: all clean

all: $(BINARY)

$(BINARY): $(EXECMAIN) $(EXECOBJS) $(OBJS)
	$(CC) -o $@ $^ $(LDFLAGS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) $(EXECOBJS) $(EXECMAIN) $(BINARY)