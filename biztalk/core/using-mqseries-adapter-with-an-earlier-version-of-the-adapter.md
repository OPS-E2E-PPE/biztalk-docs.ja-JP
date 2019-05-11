---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 38711ace8fd2c1ea328edc2ba8d4ecf83a320070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396802"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>MQSeries アダプターを使用して、アダプターの以前のバージョン
MQSeries アダプターの異なるバージョンの BizTalk Server のすべてで使用できます、同じリモート WebSphere MQ Server Windows。 次のバージョンの MQSeries アダプタで使用される COM + アプリケーションが同じ WebSphere MQSeries コンピュータに共存できるため、このことはできます。  
  
-   **MQSAgent (MQSAgent2) COM + アプリケーション**MQSeries アダプター (BizTalk Server 2006) の使用 
  
-   **MQSAgent COM + アプリケーション**MQSeries アダプター (BizTalk Server 2004) の使用  
  
-   **MQHelper COM + アプリケーション**MQSeries アダプター (BizTalk Server 2002) で使用 
  
> [!NOTE]
>  これらの COM + アプリケーションのサイド バイ サイドでインストールを構成する場合は、同じ MQSeries キューを使用してこれらの COM + アプリケーションの構成をされていることを確認します。  
  
> [!IMPORTANT]
>  MQSeries アダプタ COM + アプリケーションの以前のバージョンでは、MQSeries アダプタ COM + アプリケーションの BizTalk Server 2006 バージョンのサイド バイ サイドでインストールが、WebSphere の以前のバージョンの BizTalk Server がインストールされていない場合にのみサポートされていますMQSeries コンピュータ。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>以前のバージョンの MQSeries アダプタ COM + アプリケーションを実行している WebSphere MQSeries コンピュータに BizTalk Server 2006 バージョンの MQSeries アダプタ COM + アプリケーションをインストールするには  
  
1.  依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーするには、BizTalk Server 2006 CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行します。  
  
2.  WebSphere MQSeries コンピュータに、BizTalk Server 2006 CD の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルをコピーします。  
  
    > [!NOTE]
    >  MQSTrace.cmd ファイルこのディレクトリからにコピー WebSphere MQSeries コンピュータ MQSAgent トレース ユーティリティを使用する場合。 詳細については、MQSAgent トレース ユーティリティを参照してください[MQSeries アダプター エラーの分析トレース ツールを使用して](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)します。  
  
3.  WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行して、MQSAgent.dll にコンポーネントを手動で登録します。  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  MQSAgent.dll のコピーを同じディレクトリから、このコマンドを実行します。  
  
4.  MQSAgent コンポーネントの新しい COM + アプリケーションを作成します。  
  
    -   COM + アプリケーションを右クリックし、をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次**します。  
  
    -   クリックして**空のアプリケーションを作成する**します。  
  
    -   名前を入力します**MQSAgent2**の既定のオプションのままに**サーバー アプリケーション**有効になっており、クリックして**次**します。  
  
    -   オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**します。  
  
        > [!NOTE]
        >  このアカウントが必要接続し、配置や適切な IBM WebSphere MQ キューのアクセス許可を取得します。  
  
    -   クリックして**次**の追加**アプリケーション ロール** ダイアログ ボックス。  
  
    -   をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。  
  
    -   **[完了]** をクリックします。  
  
5.  MQSAgent.dll コンポーネントを MQSAgent2 COM + アプリケーションに追加します。  
  
    -   クリックして展開し、 **MQSAgent2** COM + アプリケーション。  
  
    -   右クリック**コンポーネント** をクリック**新規**、**コンポーネント**を COM + コンポーネント インストール ウィザードを起動し、をクリックし、**次**。  
  
    -   クリックして**新しいコンポーネントのインストール**MQSAgent.dll ファイルを参照し、をクリックし、**オープン**します。  
  
    -   **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)