---
title: WCF LOB Adapter SDK のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0987052ec5c29b321fdef8ec82a57ab582950dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363641"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK をインストールします。
インストールし、構成、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。 

## <a name="requirements"></a>必要条件 
次のコンポーネントをインストールするシステムをインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 

> [!NOTE]
> **サポートされているバージョンの一覧については**を参照してください。 
> 
> [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         Windows                                          | x86 または x64 <br/><br/>必要な OS リソースは次のとおりです。<br/> <ul><li>Microsoft は分散トランザクション コーディネーター (MSDTC) です。OleTx トランザクションをサポートするために必要</li><li>メッセージ キュー (MSMQ) をにします。信頼性の高いメッセージングをサポートするために必要な</li><li>インターネット インフォメーション サービス (IIS):IIS でアプリケーションをホストするために必要な</li><li>Windows プロセス アクティブ化サービス (WAS):WAS でアプリケーションをホストするために必要な</li></ul> |
|                             Windows Communication Foundation                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     カスタム アダプターを構築しているかどうか、またはで構築された、アダプターを使用するソリューションの開発に必要な[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 アダプターを使用するかどうかに必要な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。                                                                                                                                                                 |

## <a name="install"></a>インストール

> [!IMPORTANT]
> * Visual Studio のすべてのインスタンスを閉じる
> * **完了**セットアップは、BizTalk Server がコンピューターにインストールされていることを確認します。  

1. 実行、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**管理者として。

2. 選択**インストール Microsoft BizTalk Adapters**、し、 **Microsoft WCF LOB アダプター SDK のインストール**します。  

3. **ようこそ**画面で、**次**します。  

4. ライセンス条項に同意し、選択**次**します。  

5. **セットアップの種類の選択**インストールの種類を選択します。  

   -   共通の実行時とツールをインストールする選択**標準**します。  

   -   インストールとインストール場所にする機能を選択するには、次のように選択します。**カスタム**、しをインストールする機能を選択します。  

   -   すべての機能をインストールする選択**完了**します。  

6. **[インストール]** を選択します。  

## <a name="update-or-remove"></a>更新または削除します。

1. 開いている**プログラムと機能**します。 

2. 一覧で、次のように選択します。 **Windows Communication Foundation LOB Adapter SDK**、し、**変更**します。  

3. **ようこそ**画面で、**次**します。  

4. 次のいずれかの操作を行います。  

   - インストールするコンポーネントを選択する**変更**します。  

   - 最新のインストールのエラーを修復するには、選択**修復**します。  

   - 削除する、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、コンピューターから次のように選択します。**削除**します。  

5. インストールを変更する場合。  

   1.  **[次へ]** を選択します。  

   2.  選択**変更**、し、**完了**します。  

6. インストールを修復する場合、 **WCF LOB Adapter SDK の修復の準備完了**ダイアログ ボックスで、**修復**、し、**完了**します。  

7. アダプターを削除する場合、 **WCF LOB Adapter SDK を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**。  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK をアンインストールした後にカスタム アダプターを削除します。  

 使用して、カスタム アダプターを開発した場合、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、これらのアダプターをコンピューターに登録されているとは、次の手順を行う必要があります。  

1.  グローバル アセンブリ キャッシュ (GAC) から、カスタム アダプターを削除します。  

    1.  開く、 **Visual Studio コマンド プロンプト**します。  

    2.  カスタムの削除**アダプター .dll**を使用して、GAC から**コマンド gacutil/u**します。  

2.  Machine.config からアダプターのカスタム バインディングへの参照を削除します。  

    1.  Machine.config ファイルに移動して\<*システム ドライブ*\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

    2.  テキスト エディターを使用してファイルを開きます。  

    3.  要素の bindingExtensions、クライアントおよび bindingElementExtensions system.serviceModel\extensions 下を検索します。  

    4.  カスタム アダプターに関連する WCF バインドを削除します。  

## <a name="do-a-silent-installation"></a>サイレント インストールを実行します。  
 サイレント インストールでは、テスト シナリオや大規模なエンタープライズ展開の一部として最適です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] コマンド ライン パラメーターは、サイレント インストールを実行する AdapterFramework.msi で使用できます。  

> [!NOTE]
>  サイレント インストールを実行するには、コンピューターの管理者があります。 


1. 管理者としてコマンド プロンプトを開きます。  

2. 次のように入力します。

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   AdapterFramework.msi と組み合わせて、次のコマンド ライン オプションを使用します。  

   * 使用`/quiet`をインストールする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]サイレント モードでします。  

   * MUOPTIN を使用して、="Yes"&#124;"No"を指定する場合、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Microsoft Update と更新プログラムを確認する必要があります。  

       [はい] に設定すると[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]で Microsoft Update の更新プログラムを確認します。 設定するとまったく[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]Microsoft Update による更新プログラムをチェックしません。  

> [!NOTE]
>  コマンド ライン インストールの追加オプションを表示するには、次のように入力します。`AdapterFramework.msi /?`コマンド プロンプトでします。  

