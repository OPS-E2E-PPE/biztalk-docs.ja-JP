---
title: BizTalk Server で BizTalk RosettaNet アクセラレータ (BTARN) のアンインストール |Microsoft Docs"
description: 成果物を展開解除し、アクセラレータを BizTalk Server から削除する BTARN の構成を解除
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: a8e26119039910f398620efe478d07eeebca6f08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299970"
---
# <a name="uninstall-the-rosettanet-accelerator"></a>RosettaNet アクセラレータをアンインストールします。

## <a name="before-you-begin"></a>アンインストールの準備
  
* のみを実行する場合**Setup.exe**、アンインストール プロセスでは、ビジネス アクティビティ監視 (BAM) アイテム、BizTalk アイテム、インターネット インフォメーション サービス (IIS) 仮想ディレクトリ、およびアプリケーション プールは削除されません。  
  
* 使用した場合、 **Loopback**を 1 台のコンピューター展開用のミラー アグリーメントを作成するためのユーティリティとツールを実行、 **/無効にする <** **ホーム組織** **>** オプションでパートナーを削除する前に、 **BTARN 管理コンソール**します。  
  
* このサーバーが複数コンピュータ展開の一部である場合は実行しないでください、 **BtarnClean**ユーティリティまたは手動で BTARN アセンブリを展開解除します。 1 台のコンピューター上のアイテムを削除するには、その他のコンピューターの機能が中断されます。  すべてのサーバーから BTARN をアンインストールする場合を実行し、 **BtarnClean**ユーティリティ。 

  
## <a name="undeploy-the-artifacts"></a>成果物を展開解除します。  

展開解除する前に、BAM アイテムをバックアップすることをお勧めします。 

1. デプロイしたすべての BAM アイテムの展開を解除します。  
  
    1.  コマンド プロンプトで次のコマンドを実行します。  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  追跡 UI がインストールされているコマンド プロンプトで次のコマンドを実行します。  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  BAM の詳細については、次を参照してください[ビジネス アクティビティ監視の管理。](../../core/managing-bam.md) 
  
2.  バックアップし、BTARN 管理コンソールからすべての契約、パートナー、およびホーム組織を削除します。 使用方法については、(BTARN ヘルプの操作のノード) で「BTARN 構成の管理」トピックを参照して、 **BtarnConfig**アグリーメントとパートナーをバックアップするユーティリティ。  
  
    > [!NOTE]
    >  * 停止しを使用して BTARN によって作成された BizTalk アイテムを展開解除、 [BtarnClean](btarnclean.md)ユーティリティ。
    >  * 展開されているその他のアイテムを削除します。 参照してください[BizTalk アプリケーションを展開解除](../../core/undeploying-biztalk-applications.md)します。
  
3.  BTARN のセットアップ、MSI\Program \microsoft BizTalk Accelerator for rosettanet \sdk フォルダーを探します。 SDK フォルダーで、ダブルクリック**BTARNClean.exe**、し、 **Y**続けるには、または**N**ユーティリティの実行をキャンセルします。  
  
    > [!NOTE]
    >  サーバーが複数コンピューター展開シナリオの一部である場合は、手順 3. を省略できます。 共有リソースを削除すると、展開内の他のサーバーで、機能が中断されます。  
  
4.  作成および展開したカスタム アセンブリの展開を解除します。  
  
5.  コマンド プロンプトで \Program Files\Microsoft BizTalk Server に移動します。 <your version>\Tracking します。 次のコマンドを実行します。 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a>BTARN の構成を解除します。
  
1.  検索し、BTARN の構成を解除するには、次を実行します。  
  
     ***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**  
  
2.  コントロール パネルで、ダブルクリック**プログラム追加と削除**します。  
  
3.  **現在インストールされているプログラム**一覧で、[ **Microsoft BizTalk Accelerator for RosettaNet**、] をクリックし、**変更/削除**。  
  
4.  **プログラムのメンテナンス**ダイアログ ボックスで、**削除**、順にクリックします**次**します。  
  
5.  **概要**ダイアログ ボックスで、をクリックして**アンインストール**します。  
  
6.  **アンインストール完了**ダイアログ ボックスで、をクリックして**完了**します。  
  
    > [!NOTE]
    >  アンインストール プロセスでは、BTARN のデータベース (BTARNARCHIVE、BTARNCONFIG、および BTARNDATA) は削除されません。 それらを手動で削除する必要があります。  
  
7.  **SQL Server Management Studio** を開きます。  
  
8.  **サーバーへの接続**ダイアログ ボックスで、をクリックして**Connect**します。  
  
9. 展開、**データベース**左側のウィンドウでノード。 BTARN データベースの 1 つを右クリックし、をクリックし、**削除**します。  
  
10. **オブジェクトの削除**ダイアログ ボックスで、**既存の接続を閉じる**、順にクリックします**OK**します。  
  
