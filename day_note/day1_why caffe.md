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

想创造跟人一样的智能体，虽然这目前看起来难度挺大，但我们为什么一定要关心难或者不难呢，短暂的一生不是应该去尝试无限的可能么？一切得失真的有什么关系呢？

C就是我们主角了，这会他正对着电脑出神，每次撸代码都是这个样子，偶尔亢奋偶尔无语偶尔猛敲键盘，这也是这个时代的烙印吧，大家都觉得离我们将要亲自实现的那个奇点越来越近了，但我们内心也终究是忐忑的，或许很快就有新的生命方式取代我们了，优胜劣汰，物竞天择，或许我们的使命就是制造出真正智慧的生命体，那么这个生命体究竟该是什么样子呢？我们终究是脱离不了自我的影子，所以无论是飞升的仙还是下地狱的鬼甚至智能的机器，看起来也总是跟我们那么的神似和形似。


C这个人啊，怎么说呢？思想天马行空不受拘束，新点子一个接一个，但是可惜的是大部分都是白日做梦，自己也不敢百日实践白日梦，只能任由这些梦一个个的像过客一样一纵即逝。这会他对着眼前的代码叹息，为何这玩意不是我写出来的，唉，又错失了一个扬名立万一举功成名就的机会，可惜，可惜的很啊，转念一想，有什么关系，写不出来你，我分析分析你也是可以的嘛!到时出本书，也算是又一个走向人生巅峰的办法！急忙打开搜索引擎敲下了“caffe 源代码分析” 然后沮丧的发现，有相关内容的博客，书籍已经有太多了，C又只能默默叹口气，“生不逢时啊！”

可是生活总的继续啊!眼瞅着30了 一事无成，再过两年，到了奶娃的时间，就更没希望了！

##### 为何我如此平凡？






