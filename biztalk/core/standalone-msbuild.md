---
title: "スタンドアロン MSBUILD |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21aa3693-3788-4874-b506-6f4584fb4fd5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 584d9d5fa8e0c0f6be64d3761fabe45cd08e5a26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="standalone-msbuild"></a><span data-ttu-id="cd780-102">スタンドアロン MSBUILD</span><span class="sxs-lookup"><span data-stu-id="cd780-102">Standalone MSBUILD</span></span>
<span data-ttu-id="cd780-103">**プロジェクトがビルド**コンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構築することができます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]せずソリューション[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cd780-103">The **Project Build** component of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows you to build [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solutions without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="cd780-104">インストールする、**プロジェクトがビルド**コンポーネント、サーバーを**Project Build コンポーネント**オプション、**追加のソフトウェア カテゴリ**インストール中にします。</span><span class="sxs-lookup"><span data-stu-id="cd780-104">To install the **Project Build** component on your server, select the **Project Build Component** option in the **Additional Software category** during installation.</span></span> <span data-ttu-id="cd780-105">選択を解除する必要があります、**開発ツールおよび SDK**インストールする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]されていないコンピューターで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cd780-105">You should unselect the **Developer Tools and SDK** as you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cd780-106">MSBUILD の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。</span><span class="sxs-lookup"><span data-stu-id="cd780-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
## <a name="to-build-a-biztalk-project"></a><span data-ttu-id="cd780-107">BizTalk プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="cd780-107">To build a BizTalk project</span></span>  
  
1.  <span data-ttu-id="cd780-108">**[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd780-108">Click **Start**, and click **Run**.</span></span>  
  
2.  <span data-ttu-id="cd780-109">型**cmd**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cd780-109">Type **cmd**, and press ENTER.</span></span>  
  
3.  <span data-ttu-id="cd780-110">プロジェクト ディレクトリに切り替えて、MSBUILD コマンドを実行して BizTalk ソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="cd780-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="cd780-111">フォルダーを指すよう PATH 環境変数を設定することがあります必要があるどの msbuild.exe が存在する (\<*windows インストール ディレクトリ*> \Microsoft.NET\Framework\v4)。</span><span class="sxs-lookup"><span data-stu-id="cd780-111">You may need set the PATH environment variable to point to the folder in which msbuild.exe resides (\<*windows installation directory*>\Microsoft.NET\Framework\v4).</span></span>