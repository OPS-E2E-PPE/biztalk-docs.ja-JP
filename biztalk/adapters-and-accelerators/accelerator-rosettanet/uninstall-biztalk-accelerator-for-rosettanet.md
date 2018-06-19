---
title: BizTalk Server で BizTalk RosettaNet Accelerator (BTARN) をアンインストール |Microsoft ドキュメント"
description: 成果物を展開解除して、アクセラレータを BizTalk Server から削除する BTARN の構成を解除
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 8d289a3705eb0c127dc4d2637c2d6ffd3c122b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209842"
---
# <a name="uninstall-the-rosettanet-accelerator"></a>RosettaNet accelerator をアンインストールします。

## <a name="before-you-begin"></a>アンインストールの準備
  
* のみを実行する場合**Setup.exe**、アンインストール プロセスでは、ビジネス アクティビティ監視 (BAM) アイテム、BizTalk アイテム、インターネット インフォメーション サービス (IIS) 仮想ディレクトリ、およびアプリケーション プールは削除されません。  
  
* 使用した場合、**ループバック**、1 台のコンピューターの展開用のミラー アグリーメントを作成するユーティリティとツールを実行、**を無効にする/<** **ホーム組織** **>** でパートナーを削除する前にオプション、 **BTARN 管理コンソール**です。  
  
* このサーバーが複数コンピュータ展開の一部である場合は実行しないで、 **BtarnClean**ユーティリティまたは手動で BTARN アセンブリを展開解除します。 1 台のコンピューター上のアイテムを削除すると、他のコンピューターの機能が中断されます。  すべてのサーバーから BTARN をアンインストールする場合を実行し、 **BtarnClean**ユーティリティです。 

  
## <a name="undeploy-the-artifacts"></a>成果物を展開解除します。  

展開解除する前に、BAM アイテムをバックアップすることをお勧めします。 

1. 展開したすべての BAM アイテムの展開を解除します。  
  
    1.  コマンド プロンプトで次のコマンドを実行します。  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  追跡 UI のインストール完了を示すコマンド プロンプトで、次のコマンドを実行します。  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  BAM の詳細については、次を参照してください[ビジネス アクティビティ監視の管理。](../../core/managing-bam.md) 
  
2.  バックアップし、BTARN 管理コンソールからすべてのアグリーメント、パートナー、およびホーム組織を削除します。 参照してください「BTARN 構成の管理」(BTARN ヘルプの操作ノード) を使用する方法について、 **BtarnConfig**アグリーメントとパートナーのバックアップを作成するユーティリティです。  
  
    > [!NOTE]
    >  * 停止しを使用して BTARN によって作成された BizTalk アイテムを展開解除、 [BtarnClean](btarnclean.md)ユーティリティです。
    >  * 展開したその他のアイテムを削除します。 参照してください[BizTalk アプリケーションを展開解除](../../core/undeploying-biztalk-applications.md)です。
  
3.  BTARN セットアップ、MSI\Program \microsoft BizTalk Accelerator for rosettanet \sdk フォルダーを探します。 SDK のフォルダーをダブルクリックして**BTARNClean.exe**、し、 **Y**続けるには、または**N**ユーティリティの実行をキャンセルします。  
  
    > [!NOTE]
    >  サーバーが複数コンピューター展開シナリオで使用されている場合は、手順 3. を省略できます。 共有リソースを削除すると、展開内の他のサーバーが機能しなくなります。  
  
4.  作成および展開したすべてのカスタム アセンブリの展開を解除します。  
  
5.  コマンド プロンプトで \Program Files\Microsoft BizTalk Server に移動<your version>\Tracking です。 次のコマンドを実行します。 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a>BTARN の構成を解除します。
  
1.  次のファイルを探して実行し、BTARN の構成を解除します。  
  
     ***< ドライブ\>*****: \Program Files\\< インストール ディレクトリ\>\Configuration.exe/u**   
  
2.  コントロール パネルで、ダブルクリック**プログラム追加と削除**です。  
  
3.  **現在インストールされているプログラム**一覧で、をクリックして**Microsoft BizTalk Accelerator for RosettaNet**、クリックして**変更/削除**です。  
  
4.  **プログラムのメンテナンス**ダイアログ ボックスで、**削除**、順にクリック**次**です。  
  
5.  **概要**ダイアログ ボックスで、をクリックして**アンインストール**です。  
  
6.  **アンインストール完了**ダイアログ ボックスで、をクリックして**完了**です。  
  
    > [!NOTE]
    >  アンインストール プロセスでは、BTARN データベース (BTARNARCHIVE、BTARNCONFIG、および BTARNDATA) は削除されません。 それらを手動で削除する必要があります。  
  
7.  開いている**SQL Server Management Studio**です。  
  
8.  **サーバーへの接続**ダイアログ ボックスで、をクリックして**接続**です。  
  
9. 展開して、**データベース**左側のウィンドウ内のノードです。 BTARN データベースの 1 つを右クリックし、をクリックして**削除**です。  
  
10. **オブジェクトの削除**ダイアログ ボックスで、**既存の接続を閉じる**、順にクリック**OK**です。  
  
