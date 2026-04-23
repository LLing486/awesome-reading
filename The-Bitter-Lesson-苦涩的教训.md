# The Bitter Lesson | 苦涩的教训

> **原文链接**：http://www.incompleteideas.net/IncIdeas/BitterLesson.html  
> **作者**：Rich Sutton（里奇·萨顿）  
> **发表日期**：2019年3月13日  
> **收藏理由**：AI 领域必读经典，70年研究的核心教训——通用方法利用计算，最终远超人类知识注入式方法。

---

## 英文原文

# The Bitter Lesson

**Rich Sutton**  
*March 13, 2019*

The biggest lesson that can be read from 70 years of AI research is that general methods that leverage computation are ultimately the most effective, and by a large margin. The ultimate reason for this is Moore's law, or rather its generalization of continued exponentially falling cost per unit of computation. Most AI research has been conducted as if the computation available to the agent were constant (in which case leveraging human knowledge would be one of the only ways to improve performance) but, over a slightly longer time than a typical research project, massively more computation inevitably becomes available. Seeking an improvement that makes a difference in the shorter term, researchers seek to leverage their human knowledge of the domain, but the only thing that matters in the long run is the leveraging of computation. These two need not run counter to each other, but in practice they tend to. Time spent on one is time not spent on the other. There are psychological commitments to investment in one approach or the other. And the human-knowledge approach tends to complicate methods in ways that make them less suited to taking advantage of general methods leveraging computation. There were many examples of AI researchers' belated learning of this bitter lesson, and it is instructive to review some of the most prominent.

In computer chess, the methods that defeated the world champion, Kasparov, in 1997, were based on massive, deep search. At the time, this was looked upon with dismay by the majority of computer-chess researchers who had pursued methods that leveraged human understanding of the special structure of chess. When a simpler, search-based approach with special hardware and software proved vastly more effective, these human-knowledge-based chess researchers were not good losers. They said that "brute force" search may have won this time, but it was not a general strategy, and anyway it was not how people played chess. These researchers wanted methods based on human input to win and were disappointed when they did not.

A similar pattern of research progress was seen in computer Go, only delayed by a further 20 years. Enormous initial efforts went into avoiding search by taking advantage of human knowledge, or of the special features of the game, but all those efforts proved irrelevant, or worse, once search was applied effectively at scale. Also important was the use of learning by self play to learn a value function (as it was in many other games and even in chess, although learning did not play a big role in the 1997 program that first beat a world champion). Learning by self play, and learning in general, is like search in that it enables massive computation to be brought to bear. Search and learning are the two most important classes of techniques for utilizing massive amounts of computation in AI research. In computer Go, as in computer chess, researchers' initial effort was directed towards utilizing human understanding (so that less search was needed) and only much later was much greater success had by embracing search and learning.

In speech recognition, there was an early competition, sponsored by DARPA, in the 1970s. Entrants included a host of special methods that took advantage of human knowledge—knowledge of words, of phonemes, of the human vocal tract, etc. On the other side were newer methods that were more statistical in nature and did much more computation, based on hidden Markov models (HMMs). Again, the statistical methods won out over the human-knowledge-based methods. This led to a major change in all of natural language processing, gradually over decades, where statistics and computation came to dominate the field. The recent rise of deep learning in speech recognition is the most recent step in this consistent direction. Deep learning methods rely even less on human knowledge, and use even more computation, together with learning on huge training sets, to produce dramatically better speech recognition systems. As in the games, researchers always tried to make systems that worked the way the researchers thought their own minds worked—they tried to put that knowledge in their systems—but it proved ultimately counterproductive, and a colossal waste of researcher's time, when, through Moore's law, massive computation became available and a means was found to put it to good use.

In computer vision, there has been a similar pattern. Early methods conceived of vision as searching for edges, or generalized cylinders, or in terms of SIFT features. But today all this is discarded. Modern deep-learning neural networks use only the notions of convolution and certain kinds of invariances, and perform much better.

This is a big lesson. As a field, we still have not thoroughly learned it, as we are continuing to make the same kind of mistakes. To see this, and to effectively resist it, we have to understand the appeal of these mistakes. We have to learn the bitter lesson that building in how we think we think does not work in the long run. The bitter lesson is based on the historical observations that 1) AI researchers have often tried to build knowledge into their agents, 2) this always helps in the short term, and is personally satisfying to the researcher, but 3) in the long run it plateaus and even inhibits further progress, and 4) breakthrough progress eventually arrives by an opposing approach based on scaling computation by search and learning. The eventual success is tinged with bitterness, and often incompletely digested, because it is success over a favored, human-centric approach.

One thing that should be learned from the bitter lesson is the great power of general purpose methods, of methods that continue to scale with increased computation even as the available computation becomes very great. The two methods that seem to scale arbitrarily in this way are *search* and *learning*.

The second general point to be learned from the bitter lesson is that the actual contents of minds are tremendously, irredeemably complex; we should stop trying to find simple ways to think about the contents of minds, such as simple ways to think about space, objects, multiple agents, or symmetries. All these are part of the arbitrary, intrinsically-complex, outside world. They are not what should be built in, as their complexity is endless; instead we should build in only the meta-methods that can find and capture this arbitrary complexity. Essential to these methods is that they can find good approximations, but the search for them should be by our methods, not by us. We want AI agents that can discover like we can, not which contain what we have discovered. Building in our discoveries only makes it harder to see how the discovering process can be done.

---

## 中文翻译

# 苦涩的教训

**里奇·萨顿（Rich Sutton）**  
*2019年3月13日*

70年的人工智能研究可以汲取的最重要的教训是：利用计算的通用方法最终是最有效的，而且差距巨大。根本原因是摩尔定律，或者更准确地说，是其更广泛的概括——单位计算成本持续指数级下降。大多数人工智能研究都假设智能体可用的计算量是恒定的（在这种情况下，利用人类知识将是提高性能的唯一方法之一），但是，以比典型研究项目稍长的时间来看，大规模更多的计算不可避免地变得可用。为了在短期内寻求突破，研究人员试图利用他们对该领域的人类知识，但长期来看，唯一重要的是对计算的利用。这两者不必相互抵触，但实际上往往如此。投入在一方的时间就是从另一方抽走的时间。人们对一种方法或另一种方法存在心理上的坚持。而人类知识方法往往会使方法复杂化，使其不太适合利用通用方法来进行计算。有很多人工智能研究人员后知后觉地学会这个苦涩教训的例子，回顾一些最突出的例子是很有启发的。

在计算机象棋中，1997年击败世界冠军卡斯帕罗夫的方法是基于大规模深度搜索。当时，大多数追求利用人类对象棋特殊结构理解的研究人员都对此感到沮丧。当一种更简单的、基于搜索的方法配合特殊硬件和软件被证明要有效得多时，这些基于人类知识的象棋研究人员输不起。他们说"暴力"搜索这次可能赢了，但它不是一个通用策略，而且无论如何，这不是人们下棋的方式。这些研究人员希望基于人类输入的方法能够获胜，当它没有获胜时，他们很失望。

在计算机围棋中看到了类似的研究进展模式，只是晚了20年。最初巨大的努力投入到利用人类知识或游戏的特殊特征来避免搜索，但一旦搜索在规模上有效应用，所有这些努力都被证明是无关紧要的，或者更糟。同样重要的是利用自我对弈来学习价值函数（就像在许多其他游戏中一样，甚至在象棋中也是如此，尽管学习在1997年首次击败世界冠军的程序中没有发挥重要作用）。自我对弈学习和一般的学习，就像搜索一样，能够调用大规模计算。搜索和学习是人工智能研究中利用大量计算的两个最重要的技术类别。在计算机围棋中，就像计算机象棋一样，研究人员最初的努力方向是利用人类的理解（这样需要更少的搜索），直到很久以后，通过拥抱搜索和学习才取得了更大的成功。

在语音识别领域，1970年代有一个由DARPA赞助的早期竞赛。参赛者包括大量利用人类知识的特殊方法——关于词汇、音素、人声道的知识等。另一边是更新的方法，更具统计性质，基于隐马尔可夫模型（HMM）进行更多计算。同样，统计方法胜过了基于人类知识的方法。这导致了整个自然语言处理领域的重大变革，在几十年间逐渐发展，统计和计算开始主导该领域。最近深度学习在语音识别中的兴起是这一一致方向的最新一步。深度学习方法更少依赖人类知识，使用更多计算，结合在巨大训练集上的学习，产生了显著更好的语音识别系统。就像在游戏中一样，研究人员总是试图制造以他们认为自己的思维运作方式工作的系统——他们试图把那种知识放入他们的系统中——但这被证明最终是适得其反的，是研究人员时间的巨大浪费，因为通过摩尔定律，大规模计算变得可用，并且找到了好好利用它的方法。

在计算机视觉中也有类似的模式。早期的方法将视觉概念化为搜索边缘，或广义圆柱体，或用SIFT特征来描述。但今天所有这些都被抛弃了。现代深度学习神经网络只使用卷积的概念和某些类型的不变性，但表现要好得多。

这是一个重要的教训。作为一个领域，我们还没有彻底学到它，因为我们仍在犯同样的错误。为了看清这一点，并有效地抵制它，我们必须理解这些错误的吸引力。我们必须学到这个苦涩的教训：把我们认为我们思考的方式构建进去，从长远来看是不起作用的。苦涩的教训基于历史观察：1）人工智能研究人员经常试图将知识构建到他们的智能体中，2）这总是在短期内有帮助，并且让研究人员个人感到满足，但3）从长远来看，它会达到瓶颈甚至阻碍进一步进步，4）突破性进展最终通过一种基于通过搜索和学习扩展计算的相反方法到来。最终的成功带着苦涩，而且往往没有被完全消化，因为这是对一个受欢迎的、以人为中心的方法的超越。

从苦涩的教训中应该学到的一件事是通用方法的强大力量，这种方法即使在可用计算变得非常庞大时，仍能继续随着增加的计算而扩展。以这种方式任意扩展的两种方法是**搜索**和**学习**。

从苦涩的教训中应该学到的第二个一般性观点是，思维的实际内容是极其复杂的、不可救药的复杂；我们应该停止寻找简单的办法来思考心灵的内容，比如思考空间、物体、多智能体或对称性的简单方法。所有这些都是任意的、本质复杂的外部世界的一部分。它们不是应该被构建进去的东西，因为它们的复杂性是无穷无尽的。相反，我们应该只构建能够发现和捕获这种任意复杂性的元方法。这些方法的核心是它们能够找到好的近似，但寻找它们应该是由我们的方法来完成，而不是由我们来进行。我们想要能够像我们一样发现的AI智能体，而不是包含我们已经发现的东西的AI智能体。把我们的发现构建进去只会使我们更难看清发现过程是如何完成的。
