---
title: "MQSeries アダプターを使用して、アダプターの以前のバージョンと |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, compatibility
ms.assetid: 278a13ff-8e46-4af4-a76e-b6d4aad5b768
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba635b9bc4569f17418fc925c54c64d0fdc67461
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>MQSeries アダプターを使用して、アダプターの以前のバージョン
[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]、および [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] バージョンの MQSeries アダプタはすべて、Windows 上の同一のリモート WebSphere MQ サーバーで動作します。 このことが可能なのは、MQSeries アダプタで使用されている次のバージョンの COM+ アプリケーションを、同一の WebSphere MQSeries コンピュータ上に共存させることができるためです。  
  
-   **MQSAgent (MQSAgent2) COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]です。  
  
-   **MQSAgent COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]です。  
  
-   **MQHelper COM + アプリケーション**の MQSeries アダプタで使用される[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]です。  
  
> [!NOTE]
>  上記の COM+ アプリケーションの並列インストールを構成する場合は、各 COM+ アプリケーションが別の MQSeries キューを使用するように構成してください。  
  
> [!IMPORTANT]
>  MQSeries アダプタ COM+ アプリケーションの [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] バージョンと、以前のバージョンの MQSeries アダプタ COM+ アプリケーションの並列インストールは、以前のバージョンの BizTalk Server が WebSphere MQSeries コンピュータにインストールされていない場合にのみサポートされています。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>以前のバージョンの MQSeries アダプタ COM+ アプリケーションを実行している WebSphere MQSeries コンピュータに MQSeries アダプタ COM+ アプリケーションの BizTalk Server 2006 バージョンをインストールするには  
  
1.  [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行し、依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーします。  
  
2.  [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルを WebSphere MQSeries コンピュータにコピーします。  
  
    > [!NOTE]
    >  MQSAgent トレース ユーティリティを使用する予定がある場合は、このディレクトリから MQSTrace.cmd ファイルも WebSphere MQSeries コンピュータにコピーします。 詳細については、MQSAgent トレース ユーティリティを参照してください[トレース ツールを使用して MQSeries アダプター エラーを分析する](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)です。  
  
3.  次の手順に従い、WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行し、MQSAgent.dll にコンポーネントを手動で登録します。  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  MQSAgent.dll のコピー先と同じディレクトリからこのコマンドを実行します。  
  
4.  次の手順に従い、MQSAgent コンポーネント用の新しい COM+ アプリケーションを作成します。  
  
    -   COM + アプリケーションを右クリックし、をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次**です。  
  
    -   をクリックして**空のアプリケーションを作成する**です。  
  
    -   名前を入力します**MQSAgent2**の既定のオプションのままにして**サーバー アプリケーション**有効になっており、クリックして**次**です。  
  
    -   オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**です。  
  
        > [!NOTE]
        >  このアカウントは、適切な IBM WebSphere MQ キューに対し、CONNECT 権限と、PUT または GET (あるいはその両方) の権限を持つ必要があります。  
  
    -   をクリックして**次**の追加**アプリケーション ロール** ダイアログ ボックス。  
  
    -   をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。  
  
    -   **[完了]**をクリックします。  
  
5.  次の手順に従い、MQSAgent.dll コンポーネントを MQSAgent2 COM+ アプリケーションに追加します。  
  
    -   クリックして展開し、 **MQSAgent2** COM + アプリケーションです。  
  
    -   右クリック**コンポーネント** をクリック**新規**、**コンポーネント**COM + コンポーネント インストール ウィザードを起動し、をクリックする**次**です。  
  
    -   をクリックして**新しいコンポーネントのインストール**MQSAgent.dll ファイルを参照し、クリックして**開く**です。  
  
    -   **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタの使用](../core/using-the-mqseries-adapter.md)