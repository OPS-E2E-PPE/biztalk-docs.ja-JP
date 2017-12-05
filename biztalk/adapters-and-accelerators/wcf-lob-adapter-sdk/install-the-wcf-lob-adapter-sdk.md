---
title: "WCF LOB Adapter SDK のインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e9d4dfe5818e28e1ccd73b077c19c9d45ecb8cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK をインストールします。
インストールし、構成、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。 
  
## <a name="requirements"></a>必要条件 
次のコンポーネントをインストールするシステムをインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 

> [!NOTE]
> **サポートされているバージョンの一覧については**を参照してください。 
> 
> [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)
 
 | | | 
 | --- | --- |
 | Windows | x86 または x64 <br/><br/>OS の必要なリソースは次のとおりです。<br/> <ul><li>OleTx トランザクションをサポートするために必要な Microsoft 分散トランザクション コーディネーター (MSDTC)。</li><li>信頼できるメッセージングをサポートするために必要なメッセージ キュー (MSMQ)。</li><li>IIS でアプリケーションをホストするかどうかに必要なインターネット インフォメーション サービス (IIS)。</li><li>WAS でアプリケーションをホストするかどうかに必要な Windows プロセス アクティブ化サービス (WAS)。</li></ul> |
 |Windows Communication Foundation| | 
 | [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] | | 
 | [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] | カスタム アダプターを作成するかどうか、またはでビルドされたアダプターを使用するソリューションの開発に必要な[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] | アダプターを使用するかどうかに必要な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  |


  
## <a name="install"></a>Install

> [!IMPORTANT]
> * Visual Studio のすべてのインスタンスを閉じる
> * 行うには、**完了**セットアップは、BizTalk Server がコンピューターにインストールされていることを確認します。  
  
1.  実行、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**管理者として。
  
2.  選択**インストール Microsoft BizTalk Adapters**、し、 **Microsoft WCF LOB アダプター SDK のインストール**です。  
  
3.  **ようこそ**画面で、**次**です。  
  
4.  ライセンス契約に同意して、**[次へ]** を選択します。  
  
5.  **セットアップの種類の選択**インストールの種類を選択します。  
  
    -   一般的なランタイムとツールをインストールする選択**標準**です。  
  
    -   を、必要な機能をインストールして、インストール場所を選択する**カスタム**、しをインストールする機能を選択します。  
  
    -   すべての機能をインストールする選択**完了**です。  
  
6.  **[インストール]**を選択します。  
  
## <a name="update-or-remove"></a>更新または削除
  
1.  開いている**プログラムと機能**します。 
  
2.  一覧で、次のように選択します。 **Windows Communication Foundation LOB Adapter SDK**、し、**変更**です。  
  
3.  **ようこそ**画面で、**次**です。  
  
4.  次のいずれかの操作を行います。  
  
    -   インストールするコンポーネントを選択する**変更**です。  
  
    -   最新のインストールのエラーを修復するには、次のように選択します。**修復**です。  
  
    -   削除する、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、コンピューターから選択**削除**です。  
  
5.  選択する場合、インストールを変更します。  
  
    1.  **[次へ]** を選択します。  
  
    2.  選択**変更**、し、**完了**です。  
  
6.  インストールを修復する場合、 **WCF LOB Adapter SDK を修復する準備ができて**ダイアログ ボックスで、**修復**、し、**完了**です。  
  
7.  アダプターを削除する場合、 **WCF LOB Adapter SDK を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**です。  
  
  
#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK をアンインストールした後にカスタム アダプターを削除します。  

 使用して、カスタム アダプターを開発している場合、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]コンピューターにこれらのアダプターを登録しても、次の手順を完了する必要があります。  
  
1.  グローバル アセンブリ キャッシュ (GAC) から、カスタム アダプターを削除します。  
  
    1.  開く、 **Visual Studio コマンド プロンプト**です。  
  
    2.  ユーザー設定を削除する**アダプター .dll**を使用して、GAC から**コマンド gacutil/u**です。  
  
2.  Machine.config からカスタム アダプター バインドへの参照を削除します。  
  
    1.  下にある machine.config ファイルに移動して\<*システム ドライブ*\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
    2.  テキスト エディターを使用してファイルを開きます。  
  
    3.  要素 bindingExtensions、クライアントおよび system.serviceModel\extensions bindingElementExtensions を検索します。  
  
    4.  カスタム アダプターに関連する WCF バインドを削除します。  
  
## <a name="do-a-silent-installation"></a>サイレント インストールを行う  
 サイレント インストールでは、テスト シナリオや大規模なエンタープライズ展開の一部として最適です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]コマンド ライン パラメーターを提供することができますと共に使用する AdapterFramework.msi をサイレント インストールを実行します。  
 
> [!NOTE]
>  サイレント インストールを実行するには、コンピューターの管理者をおく必要があります。 

  
1.  管理者としてコマンド プロンプトを開きます。  
  
2.  次のように入力します。
  
    ```  
    AdapterFramework.msi /quiet MUOPTIN=”Yes”  
    ```  
  
    AdapterFramework.msi と組み合わせて、次のコマンド ライン オプションを使用します。  
  
    * 使用して`/quiet`をインストールする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サイレント モードでします。  
  
    * MUOPTIN を使用して ="Yes"&#124;"No"を指定する場合に、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Microsoft Update と更新プログラムを確認する必要があります。  
    
        [はい] に設定すると[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]Microsoft Update から更新プログラムをチェックします。 設定するとまったく[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]Microsoft Update による更新プログラムをチェックしません。  
  
> [!NOTE]
>  コマンド ライン インストールの追加オプションを表示するには、次のように入力します。`AdapterFramework.msi /?`コマンド プロンプトでします。  
  
