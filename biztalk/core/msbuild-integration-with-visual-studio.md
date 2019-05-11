---
title: MSBUILD と Visual Studio の統合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01b0f59d73c48dba994b0c57cae3b4c697e426b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264539"
---
# <a name="msbuild-integration-with-visual-studio"></a><span data-ttu-id="c4f59-102">MSBUILD の Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="c4f59-102">MSBUILD Integration with Visual Studio</span></span>
<span data-ttu-id="c4f59-103">Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージド プロジェクトに関するビルド情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="c4f59-103">Visual Studio uses the MSBUILD project file format to store build information about managed projects including BizTalk projects.</span></span> <span data-ttu-id="c4f59-104">プロジェクトごとに生成される .btproj ファイルには、プロジェクトの設定を追加して、Visual Studio を使用して変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="c4f59-104">Project settings added and changed through Visual Studio are reflected in the .btproj file that is generated for each project.</span></span> <span data-ttu-id="c4f59-105">Visual Studio では、MSBUILD のホスト インスタンスを使用して、BizTalk プロジェクトでは、構築、つまりまたは同一の結果をコマンドラインから Visual Studio で BizTalk プロジェクトを構築できます。</span><span class="sxs-lookup"><span data-stu-id="c4f59-105">Visual Studio uses a hosted instance of MSBUILD to build BizTalk projects, meaning that a BizTalk project can be built in Visual Studio or from the command line, with identical results.</span></span>  
  
 <span data-ttu-id="c4f59-106">MSBUILD の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)します。</span><span class="sxs-lookup"><span data-stu-id="c4f59-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="c4f59-107">次の手順では、MSBUILD を使用してコマンドラインからサンプル BizTalk プロジェクトをビルドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4f59-107">The following procedure shows you how to use MSBUILD to build a sample BizTalk project from command line.</span></span>  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a><span data-ttu-id="c4f59-108">コマンドラインからの BizTalk プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c4f59-108">To build a BizTalk project from a command line</span></span>  
  
1.  <span data-ttu-id="c4f59-109">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="c4f59-109">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="c4f59-110">プロジェクト ディレクトリに切り替えるし、BizTalk ソリューションをビルドする MSBUILD コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4f59-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c4f59-111">ソリューションがなど、BizTalk、および BizTalk 以外のプロジェクトを含めることができます、C#クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="c4f59-111">The solution may contain BizTalk and non-BizTalk projects, such as a C# class library.</span></span>