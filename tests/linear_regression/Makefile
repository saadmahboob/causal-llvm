ROOT = ../..
TARGETS = linear_regression
LIBS = pthread dl
ARGS = linear_regression_datafiles/key_file_500MB.txt

include $(ROOT)/common.mk

setup: linear_regression_datafiles/key_file_500MB.txt

linear_regression_datafiles/%:
	wget http://mapreduce.stanford.edu/datafiles/linear_regression.tar.gz
	tar xvzf linear_regression.tar.gz
	rm linear_regression.tar.gz

test:: linear_regression setup
	$(PRELOAD_VAR)=$(ROOT)/libcausal.$(SHLIB_SUFFIX) ./linear_regression $(ARGS)
