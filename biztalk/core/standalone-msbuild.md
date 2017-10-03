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
# <a name="standalone-msbuild"></a>スタンドアロン MSBUILD
**プロジェクトがビルド**コンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構築することができます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]せずソリューション[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 インストールする、**プロジェクトがビルド**コンポーネント、サーバーを**Project Build コンポーネント**オプション、**追加のソフトウェア カテゴリ**インストール中にします。 選択を解除する必要があります、**開発ツールおよび SDK**インストールする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]されていないコンピューターで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
 MSBUILD の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。  
  
## <a name="to-build-a-biztalk-project"></a>BizTalk プロジェクトをビルドするには  
  
1.  **[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。  
  
2.  型**cmd**、ENTER キーを押します。  
  
3.  プロジェクト ディレクトリに切り替えて、MSBUILD コマンドを実行して BizTalk ソリューションを構築します。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  フォルダーを指すよう PATH 環境変数を設定することがあります必要があるどの msbuild.exe が存在する (\<*windows インストール ディレクトリ*> \Microsoft.NET\Framework\v4)。