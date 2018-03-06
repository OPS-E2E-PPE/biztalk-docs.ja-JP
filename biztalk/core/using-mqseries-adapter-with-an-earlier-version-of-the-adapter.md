---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: 
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>MQSeries アダプターを使用して、アダプターの以前のバージョン
MQSeries アダプターの異なるバージョンの BizTalk Server のすべてで、作業できる、同じリモートの WebSphere MQ Server Windows です。 このことが可能なのは、MQSeries アダプタで使用されている次のバージョンの COM+ アプリケーションを、同一の WebSphere MQSeries コンピュータ上に共存させることができるためです。  
  
-   **MQSAgent (MQSAgent2) COM + アプリケーション**MQSeries アダプター (BizTalk Server 2006) の使用 
  
-   **MQSAgent COM + アプリケーション**MQSeries アダプター (BizTalk Server 2004) と使用  
  
-   **MQHelper COM + アプリケーション**MQSeries アダプター (BizTalk Server 2002) の使用 
  
> [!NOTE]
>  上記の COM+ アプリケーションの並列インストールを構成する場合は、各 COM+ アプリケーションが別の MQSeries キューを使用するように構成してください。  
  
> [!IMPORTANT]
>  MQSeries アダプタ COM + アプリケーションの以前のバージョンで、MQSeries アダプタ COM + アプリケーションの BizTalk Server 2006 バージョンをサイド バイ サイド インストールは、WebSphere に BizTalk Server の以前のバージョンがインストールされていない場合にのみサポートします。MQSeries コンピュータ。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>以前のバージョンの MQSeries アダプタ COM+ アプリケーションを実行している WebSphere MQSeries コンピュータに MQSeries アダプタ COM+ アプリケーションの BizTalk Server 2006 バージョンをインストールするには  
  
1.  依存関係ファイル MSVCR80.dll および MSVCP80.dll を WebSphere MQSeries コンピュータにコピーするには、BizTalk Server 2006 CD の \Platform\BootStrap\ ディレクトリから Bootstrap.msi を実行します。  
  
2.  WebSphere MQSeries コンピュータに BizTalk Server 2006 CD 上の \Msi\Program Files\ ディレクトリから MQSAgent.dll ファイルをコピーします。  
  
    > [!NOTE]
    >  MQSAgent トレース ユーティリティを使用する予定がある場合は、このディレクトリから MQSTrace.cmd ファイルも WebSphere MQSeries コンピュータにコピーします。 詳細については、MQSAgent トレース ユーティリティを参照してください[トレース ツールを使用して MQSeries アダプター エラーを分析する](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)です。  
  
3.  次の手順に従い、WebSphere MQSeries コンピュータで regsvr32 mqsagent.dll を実行し、MQSAgent.dll にコンポーネントを手動で登録します。  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  MQSAgent.dll のコピー先と同じディレクトリからこのコマンドを実行します。  
  
4.  次の手順に従い、MQSAgent コンポーネント用の新しい COM+ アプリケーションを作成します。  
  
    -   COM + アプリケーションを右クリックし、クリックして **新規**, 、**アプリケーション** を表示する、 **COM + アプリケーション インストール ウィザード**  をクリック **次**します。  
  
    -   クリックして **空のアプリケーションを作成する**です。  
  
    -   名前を入力します **MQSAgent2**, の既定のオプションのままにして **サーバー アプリケーション** 有効になっており、クリックして **次**します。  
  
    -   オプションを選択する **このユーザー**, 、適切なアカウント情報を入力し、クリックして **次**します。  
  
        > [!NOTE]
        >  このアカウントは、適切な IBM WebSphere MQ キューに対し、CONNECT 権限と、PUT または GET (あるいはその両方) の権限を持つ必要があります。  
  
    -   をクリックして **次** 追加 **アプリケーション ロール**  ダイアログ ボックス。  
  
    -   をクリックして **次** 上、 **にユーザー ロールを追加**  ダイアログ ボックス。  
  
    -   **[完了]**をクリックします。  
  
5.  次の手順に従い、MQSAgent.dll コンポーネントを MQSAgent2 COM+ アプリケーションに追加します。  
  
    -   クリックして展開し、 **MQSAgent2** COM + アプリケーションです。  
  
    -   右クリック **コンポーネント**  をクリック **新規**, 、**コンポーネント** を COM + コンポーネント インストール ウィザードを起動し、をクリックし、 **次**します。  
  
    -   クリックして **新しいコンポーネントのインストール**, を MQSAgent.dll ファイルを参照してクリックして **開く**します。  
  
    -   **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)