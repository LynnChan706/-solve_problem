why deep learning？ why caffe?

```
Caffe::Caffe()
    : cublas_handle_(NULL), curand_generator_(NULL), random_generator_(),
    mode_(Caffe::CPU),
    solver_count_(1), solver_rank_(0), multiprocess_(false) {
  // Try to create a cublas handler, and report an error if failed (but we will
  // keep the program running as one might just want to run CPU code).
  if (cublasCreate(&cublas_handle_) != CUBLAS_STATUS_SUCCESS) {
    LOG(ERROR) << "Cannot create Cublas handle. Cublas won't be available.";
  }
  // Try to create a curand handler.
  if (curandCreateGenerator(&curand_generator_, CURAND_RNG_PSEUDO_DEFAULT)
      != CURAND_STATUS_SUCCESS ||
      curandSetPseudoRandomGeneratorSeed(curand_generator_, cluster_seedgen())
      != CURAND_STATUS_SUCCESS) {
    LOG(ERROR) << "Cannot create Curand generator. Curand won't be available.";
  }
}
```

##### 我们做的每件事都会有它背后的意义，自古至今，人类构建了各种各样的工具（有形的，无形的），来实现我们的梦想。虽然梦想各种各样，但无一例外都需要我们用自己的努力来支撑着将他实现。

*我们希望能解决实现想法过程中的各种问题，我们的第一个有问题是*

#### why deeplearning? 为什么是深度学习？

其实这仍旧是我们最伟大的梦想之一，我们想造一个跟自己一样的 “东西” 
古往今来，我们不断的通过模仿来实现梦想，我们想飞，看到飞的鸟，就明白了一件事，只要我们努力去做，总有一天我们也能飞起来，原因当然很简单，因为已经有成功的范例，所以这个结论是一定的，其它的只是时间问题了，一步一步的总会走到我们要的未来。


*我始终相信，类人的智能总有实现的那一天*

*这就是我们主人公诞生的第一天的世界*

他想要解决的问题是，类人智能

想创造跟人一样的智能体