---
title: スタンドアロン MSBUILD |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21aa3693-3788-4874-b506-6f4584fb4fd5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb728201c4c022b093c69cd282666e09d60f6b11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392898"
---
# <a name="standalone-msbuild"></a>スタンドアロン MSBUILD
**プロジェクトがビルド**のコンポーネントである[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]せず、BizTalk Server ソリューションを構築することができます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 インストールする、**プロジェクトがビルド**コンポーネント、サーバーを**Project Build コンポーネント**オプション、**追加のソフトウェア カテゴリ**インストール中にします。 選択を解除する必要があります、**開発ツールおよび SDK**をインストールするよう[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のないコンピューターで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
 MSBUILD の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)します。  
  
## <a name="to-build-a-biztalk-project"></a>BizTalk プロジェクトをビルドするには  
  
1.  **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。  
  
2.  型**cmd**、ENTER キーを押します。  
  
3.  プロジェクト ディレクトリに切り替えるし、BizTalk ソリューションをビルドする MSBUILD コマンドを実行します。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  フォルダーを指すように PATH 環境変数を設定することがあります必要があるどの msbuild.exe が存在する (\<*windows インストール ディレクトリ*\>\Microsoft.NET\Framework\v4)。