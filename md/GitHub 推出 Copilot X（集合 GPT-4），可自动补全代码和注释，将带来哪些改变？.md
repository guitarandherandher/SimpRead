> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.zhihu.com](https://www.zhihu.com/question/591312865/answer/2949607879)

[https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/](https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/)

![](https://picx.zhimg.com/6cc78144fed4969434ee35c1f5b0344f_l.jpg?source=1940ef5c)段小草​​

**关于大家问的收费问题… 学生认证啊！edu 邮箱就可解决！学生计划链接：**

[https://education.github.com/](https://education.github.com/)

* * *

官网：[https://github.com/features/preview/copilot-x](https://github.com/features/preview/copilot-x)

快去排队，一定记得四款产品要分别加入 waitlist，而不是点一个就行了。

- Copilot Chat: [https://github.com/github-copilot/chat_waitlist_signup/join](https://github.com/github-copilot/chat_waitlist_signup/join)

- Copilot for Pull Request: [Copilot for PRs](https://copilot4prs.githubnext.com/login)

- Copilot CLI: [GitHub Next | Copilot for CLI](https://githubnext.com/projects/copilot-cli/)

- Copilot Doc: [GitHub Next | Copilot for Docs](https://githubnext.com/projects/copilot-for-docs)

官方介绍：[https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/](https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/)

简单来说就是：

> 采用了 OpenAI 的新 GPT-4 模型，而且还为 Copilot 引入了聊天和语音，并让 Copilot pull requests，命令行和文档来回答有关项目的问题。

四个功能也很直观，从名字上就能看出来作用：

- Copilot Chat: **使用 GitHub Copilot 聊天在编辑器中类似 ChatGPT 的体验：**将一个聊天界面引入编辑器，该界面专注于开发人员方案，并与 VS Code 和 Visual Studio 本机集成。这远远超出了建议代码的作用。GitHub Copilot Chat 不仅仅是一个聊天窗口。它可以识别开发人员键入的代码、显示的错误消息，并将其深度嵌入到 IDE 中。开发人员可以深入分析和解释代码块的用途，生成单元测试，甚至获得对错误的建议修复。GitHub Copilot Chat 建立在 OpenAI 和微软对 ChatGPT 和新 Bing 所做的工作之上。它还将加入语音到代码 AI 技术扩展，称之为 GitHub Copilot Voice，开发人员可以口头提供自然语言提示。

- Copilot for Pull Request: 对于 PR 和项目管理的帮助。

- Copilot CLI: 终端是开发人员花费最多时间的地方。但即使是最熟练的开发人员也需要滚动浏览许多页面才能记住许多命令的精确语法。这就是我们推出 [GitHub Copilot CLI](https://githubnext.com/projects/copilot-cli/) 的原因。它可以编写命令和循环，并抛出晦涩的查找标志以满足您的查询。

- Copilot Doc: 它使用聊天界面为用户提供 AI 生成的对文档问题的回答，包括开发人员对他们正在使用的语言、框架和技术提出的问题。我们从 [React](https://react.dev/)、[Azure Docs](https://learn.microsoft.com/en-us/azure/?product=popular) 和 [MDN](https://developer.mozilla.org/) 的文档开始，因此我们可以与这些项目的开发人员和用户一起快速学习和迭代。将来也会**我在努力将此功能引入任何组织的仓库和内部文档。**

**看完以后感想就是：程序员的自我革命… 太狠了。我身边已经有使用 ChatGPT 零基础（从下载安装环境开始，全程没有跳出 ChatGPT 或者 NewBing）学习写代码并成功运行的朋友了…**

**「出现了在 GPT 帮助下以分钟进化的人类」——不是在开玩笑。**

![](https://pic1.zhimg.com/v2-be06bed2527411c02f4ce4563c305e80_l.jpg?source=1940ef5c)DBinary​​

嘿嘿，这部分其实可以用 Cursor 率先体验一下，Cursor 就是调用的是 Copilot 的接口（也是 GPT-4）模型的。

用了一段时间了，实际体验是简单的那种一搜索一大片的代码写起来没什么问题，但是稍微复杂点的代码，就需要改了，而且很多细节问题拐不过弯来, 比如我想用一维数组当二维矩阵来用, 他就写一些乱七八糟的玩意出来了。

为了贴合这个阿斗，我特意捏了一个简单的游戏引擎出来，并为它量身捏了一款脑瘫版类 c 语 compiler，好让它帮我打工写游戏。但是，稍微要动点脑子的代码（根本不能叫复杂，稍微比 easy 难一丢丢的问题）基本 9 成需要自己改过，比如我让他帮我写一个迷宫生成算法：

![](https://pic1.zhimg.com/v2-76a123bf65d3a0c0edfc78c0a9ad7d10_r.jpg?source=1940ef5c)

然后它帮我写了一段：

```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define ROW 20
#define COL 20

int map[ROW][COL];

void printMaze() {
    for (int i = 0; i < ROW; i++) {
        for (int j = 0; j < COL; j++) {
            if (map[i][j] == 1) {
                printf("■ ");
            } else {
                printf("□ ");
            }
        }
        printf("\n");
    }
}

void generateMaze() {
    srand((unsigned)time(NULL));
    for (int i = 0; i < ROW; i++) {
        for (int j = 0; j < COL; j++) {
            if (i == 0 || j == 0 || i == ROW - 1 || j == COL - 1) {
                map[i][j] = 1;
            } else if (rand() % 3 == 0) {
                map[i][j] = 1;
            } else {
                map[i][j] = 0;
            }
        }
    }
    map[0][0] = 0;
    map[ROW - 1][COL - 1] = 0;
}

int main() {
    generateMaze();
    printMaze();
    return 0;
}
```

可是入口和出口，都不是连通的

![](https://pic1.zhimg.com/v2-b23dab8a451cb44b123bb82b4d061dc8_r.jpg?source=1940ef5c)

我尝试让他修复这个 bug, 显然这个为难它了, 尝试各种提示也不管用，不讲码德, 拿一些根本不顶用的代码来骗，来忽悠我.

![](https://pic1.zhimg.com/v2-994a3995c22345739f373d5909728b32_r.jpg?source=1940ef5c)![](https://picx.zhimg.com/v2-3894f2e965615513efd861f06e4200bb_r.jpg?source=1940ef5c)

没办法, 我只好在这个代码的基础上做点微调 (感觉 90% 的工作其实还是我干的), 包括固定了随机数种子，然后用类似炼丹的方式变换种子终于搞出了一个至少能通关的地图了

![](https://pic1.zhimg.com/v2-cb09e7aa485c77d5b85eacca55bf6a64_r.jpg?source=1940ef5c)

附上代码

```
#name "main"
#include "stdlib.h"

export void GameOnTrigger(string id)
{
   
}

export void GameOnDie()
{
   sleep(3000);
   defeat();
}

export void GameOnFood(string id)
{
    setspeed(0);
    sleep(1000);
    victory();
}

void drawmap(int x,int y)
{
    drawrect(x*20,y*20,20,20,1,1,1,1);
}

#define ROW 40
#define COL 40

export void GameInitialize(int width,int height)
{
    int i,j;
    createplayer(8,8,10);
    createfood(800-8,800-8,1,1,0,0,16,"food");
    setlayer(0);
    clearmap(1,0,0,0);
    rand();
    rand();
    rand(); 
    rand();  
    rand(); 
    rand();
    rand();
    rand();
    rand();
    rand();
   //就这段ai写的
    for (i = 0; i < ROW; i++) {
        for (j = 0; j < COL; j++) {
           if (rand() % 3 != 0) 
            {
                drawmap(i,j);
            }
        }
    }
    drawmap(0,0);
    drawmap(ROW - 1,COL - 1);
   //到这里
    wait(3000);
}


export void GameRun(int elapsed)
{

}
```

还有几个 AI 辅助创作的，也差不多，体验就是，有用，但感觉也没多有用（营销号就不要整天吹什么取代了，光贴个生成代码的截图搞的跟真的一样，有本事你点下编译啊~）

![](https://pica.zhimg.com/v2-a1bd2d5600a158e0793cd28806e1516c_r.jpg?source=1940ef5c)

附上代码

```
#name "main"
#include "stdlib.h"

int ate = 0;

export void GameOnTrigger(string id)
{
   
}

export void GameOnDie()
{
   sleep(3000);
   defeat();
}

export void GameOnFood(string id)
{
   ate++;
   if (ate==4)
   {
      setspeed(0);
      sleep(1000);
      victory();
   }
}

export void thread1()
{
   float angle1;
   float angle2;
   float angle3;
   float angle4;
   float angle5;
   while (1)
   {
      sleep(150);
      setlayer(1);
      clearmap(0,1,1,1);
      drawcircle(400,400,400,16,1,0,0,0);
      drawcircle(400,400,300,16,1,0,0,0);
      drawcircle(400,400,200,16,1,0,0,0);
      drawcircle(400,400,100,16,1,0,0,0);
      drawcircle(400,400,50,16,1,0,0,0);

      angle1=angle1+3;
      angle2=angle2+6;
      angle3=angle3+9;
      angle4=angle4+12;
      angle5=angle5+15;
      //就这段ai写的
      drawsolidcircle(400+cos(angle1/180.0*3.14159)*400,400+sin(angle1/180.0*3.14159)*400,32,1,1,1,1);
      drawsolidcircle(400+cos(angle2/180.0*3.14159)*300,400+sin(angle2/180.0*3.14159)*300,32,1,1,1,1);
      drawsolidcircle(400+cos(angle3/180.0*3.14159)*200,400+sin(angle3/180.0*3.14159)*200,32,1,1,1,1);
      drawsolidcircle(400+cos(angle4/180.0*3.14159)*100,400+sin(angle4/180.0*3.14159)*100,32,1,1,1,1);
      drawsolidcircle(400+cos(angle5/180.0*3.14159)*50,400+sin(angle5/180.0*3.14159)*50,32,1,1,1,1);
      //////
   }
}


export void GameInitialize(int width,int height)
{
    createplayer(400,400,16);
    createfood(16,16,1,1,0,0,16,"food");
    createfood(800-16,16,1,1,0,0,16,"food");
    createfood(16,800-16,1,1,0,0,16,"food");
    createfood(800-16,800-16,1,1,0,0,16,"food");
    createthread("thread1",1);
    wait(3000);
}


export void GameRun(int elapsed)
{

}
```

![](https://picx.zhimg.com/db71edd8da1c9095946a0814daa0cb20_l.jpg?source=1940ef5c)wgwang

GitHub Copilot X 目前处于预览模式，已加入 waitlist

![](https://picx.zhimg.com/v2-680d807cf314024c26434ab5c4212c03_r.jpg?source=1940ef5c)

GitHub Copilot X 是 GitHub Copilot 的一个新版本，是一种基于人工智能的代码补全工具，使用 OpenAI 的 Codex 模型根据自然语言输入或现有代码生成代码建议。 GitHub Copilot X 采用了 OpenAI 最新的 GPT-4 模型，可以根据开发人员的上下文和偏好生成更准确、更个性化的代码建议。

GitHub Copilot X 引入了几个新功能，旨在增强开发人员在整个开发生命周期中的人工智能辅助体验：

1.  编辑器中的聊天界面，允许开发人员使用自然语言、语音命令或代码片段与 GitHub Copilot 交互。聊天界面可以帮助开发人员编写和调试代码、生成单元测试、解释代码块、修复错误等。
2.  pull request 集成，使 GitHub Copilot 能够自动生成 PR 描述、建议缺失的单元测试、审核代码更改并提供反馈。 命令行界面，允许开发人员从任何终端或 shell 使用 GitHub Copilot。
3.  命令行界面可以帮助开发人员创建新项目、运行命令、安装依赖等。 文档集成，使 GitHub Copilot 能够使用自然语言或代码示例回答文档页面上的问题。
4.  文档集成可以帮助开发人员学习新概念、找到相关信息并解决问题。

![](https://pic1.zhimg.com/v2-c869bba79f719939899572d8e427e769_r.jpg?source=1940ef5c)![](https://picx.zhimg.com/v2-1023ca4e3b9204177d848dc36a7f3383_r.jpg?source=1940ef5c)

GitHub Copilot X 的这些新功能为开发人员提供了更高效、更智能的代码编写和协作体验。它可以帮助开发人员更快地编写代码，减少手动输入和纠错的时间，提高开发效率。此外，它还可以提高代码的质量和可维护性，减少错误和漏洞的风险。

“X” 代表一个占位符，表示我们希望 GitHub Copilot 可用的位置，以及我们期望它能够做什么（例如 “Copilot <for pull requests>”、“Copilot <for security>”）。它将产品从单一体验、代码完成扩展到跨开发人员工作流程的 X 体验。GitHub Copilot 明天总是需要比现在多得多。

此外，“X” 表示我们打算对开发人员成就产生的影响程度。因此，这是一份意向声明，也是对开发人员的承诺，因为我们将共同进入人工智能时代。我们希望业界对 GitHub Copilot 充满信心，并希望工程团队将其视为_未来发展的纽带_。

GitHub Copilot X 目前是 GitHub 未来愿景的代表，而不是 GitHub Copilot 的可用产品。随着我们继续设计、测试和构建符合 GitHub Copilot X 愿景的功能，我们也在花时间确定向我们的客户提供这些功能的最佳方式。