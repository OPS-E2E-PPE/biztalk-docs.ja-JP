---
title: "Visual Studio での MSBUILD の統合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4a639945881625dd697798080c913ec0e5e3a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msbuild-integration-with-visual-studio"></a><span data-ttu-id="24b37-102">MSBUILD の Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="24b37-102">MSBUILD Integration with Visual Studio</span></span>
<span data-ttu-id="24b37-103">Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージ プロジェクトに関するビルド情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="24b37-103">Visual Studio uses the MSBUILD project file format to store build information about managed projects including BizTalk projects.</span></span> <span data-ttu-id="24b37-104">Visual Studio から追加および変更されたプロジェクト設定は、プロジェクトごとに生成される .btproj ファイルに反映されます。</span><span class="sxs-lookup"><span data-stu-id="24b37-104">Project settings added and changed through Visual Studio are reflected in the .btproj file that is generated for each project.</span></span> <span data-ttu-id="24b37-105">Visual Studio は、MSBUILD のホストされたインスタンスを使用して BizTalk プロジェクトをビルドします。つまり、BizTalk プロジェクトは Visual Studio でビルドすることも、コマンド ラインからビルドすることもできます。結果はどちらも同じです。</span><span class="sxs-lookup"><span data-stu-id="24b37-105">Visual Studio uses a hosted instance of MSBUILD to build BizTalk projects, meaning that a BizTalk project can be built in Visual Studio or from the command line, with identical results.</span></span>  
  
 <span data-ttu-id="24b37-106">MSBUILD の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。</span><span class="sxs-lookup"><span data-stu-id="24b37-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="24b37-107">次の手順は、MSBUILD を使用してサンプル BizTalk プロジェクトをコマンド ラインからビルドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="24b37-107">The following procedure shows you how to use MSBUILD to build a sample BizTalk project from command line.</span></span>  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a><span data-ttu-id="24b37-108">BizTalk プロジェクトをコマンド ラインからビルドするには</span><span class="sxs-lookup"><span data-stu-id="24b37-108">To build a BizTalk project from a command line</span></span>  
  
1.  <span data-ttu-id="24b37-109">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="24b37-109">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="24b37-110">プロジェクト ディレクトリに切り替えて、MSBUILD コマンドを実行して BizTalk ソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="24b37-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="24b37-111">ソリューションには、BizTalk プロジェクトおよび C# クラス ライブラリなどの非 BizTalk プロジェクトを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="24b37-111">The solution may contain BizTalk and non-BizTalk projects, such as a C# class library.</span></span>