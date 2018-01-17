---
title: "SharePoint Services 送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36aadbc2-316f-4e1c-a5a8-b162470acf9e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f424d3ad1b38316802585aefca0a49bf2f67f0a2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="configure-sharepoint-services-send-port"></a>SharePoint Services 送信ポートの構成
このトピックでは、静的送信ポートと動的送信ポートを比較し、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 送信ポートを作成する手順も示します。 具体的な内容は次のとおりです。  
  
 [動的送信ポートと静的な送信ポート](../core/configure-sharepoint-services-send-port.md#BKMK_StaticvsDynamic)  
  
 [静的送信ポートを作成します。](../core/configure-sharepoint-services-send-port.md#BKMK_StaticSend)  
  
 [動的送信ポートを作成します。](../core/configure-sharepoint-services-send-port.md#BKMK_DynamicSend)  
  
##  <a name="BKMK_StaticvsDynamic"></a> 動的送信ポートと静的な送信ポート  
  
||静的送信ポート|動的送信ポート|  
|-|----------------------|-----------------------|  
|異なるアダプターに 1 つの送信ポートを使用する。|いいえ<br /><br /> 静的送信ポートを作成するときは、トランスポートの種類が必要です。|はい<br /><br /> 通常、動的送信ポートはオーケストレーションに追加されます。 トランスポートの種類はオーケストレーション ロジックで構成されます。|  
|URL のように、異なる送信ポート プロパティに 1 つの送信ポートを使用する。|いいえ<br /><br /> 静的送信ポートを作成するときは、URL など、一部のアダプター プロパティを構成する必要があります。|可<br /><br /> 通常、動的送信ポートはオーケストレーションに追加されます。 プロパティはオーケストレーション ロジックで構成されます。|  
|既定の送信ハンドラーを使用する必要がある。|いいえ<br /><br /> 送信ハンドラーは、送信ポートを作成するときに構成できます。|いいえ<br /><br /> 送信ハンドラーは、送信ポートを作成するときに構成できます。|  
|メッセージの送信先が不明な場合に使用する。|いいえ<br /><br /> 静的送信ポートを作成するときは、トランスポートの種類と場所を指定します。|可<br /><br /> 送信先は、オーケストレーションおよびコンテンツ ベースのルーティング シナリオで構成できます。 メッセージの送信先をフィルター処理するためにルールを使用することもできます。|  
|複数のパートナーにメッセージを送信するために 1 つの送信ポートを使用する。|いいえ<br /><br /> 静的送信ポートを作成するときは、トランスポートの種類と場所を指定します。|はい<br /><br /> 通常、動的送信ポートはオーケストレーションに追加されます。 プロパティはオーケストレーション ロジックで構成され、指定するルールに基づいて、メッセージを複数のパートナーに送信できます。|  
  
##  <a name="BKMK_StaticSend"></a> 静的送信ポートを作成します。  
 静的送信ポートを作成するときは、送信ポートはトランスポートの種類に関連付けられている既定の送信ハンドラーを使用します。 使用する場合、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプター、既定の送信ハンドラーは**BizTalkServerApplication**です。 を新しい送信ハンドラーを追加する手順を参照してください [をアダプター ハンドラーを作成する方法](http://go.microsoft.com/fwlink/p/?LinkId=263646)します。  
  
 静的送信ポートを作成するには  
  
1.  **BizTalk Server 管理コンソール**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーション。  
  
2.  右クリック **送信ポート**, 、クリックして **新規**, 、順にクリック **静的な一方向送信ポート**します。  
  
    > [!IMPORTANT]
    >  A**静的な送信請求-応答送信ポート**で構成することはありません、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプター。  
  
3.  **プロパティ**, をクリックして **Windows SharePoint Services** で、 **型** ドロップダウン リストです。 入力、 **名前**, 、**送信ハンドラー**, 、および **送信パイプライン** プロパティです。  
  
4.  クリックして **構成**します。 **プロパティ**, 、次を構成します。  
  
    |||  
    |-|-|  
    |アダプター Web サービス ポート|**必要な**です。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプター Web サービスをホストしている IIS Web サイト上で構成されるポート。<br /><br /> 既定ではポート **80**, 、これは、標準の HTTP ポート。 80 以外のポートを使用するときは、この値を更新します。|  
    |Timeout|**必要な**です。 この値により、アダプターが Web サービスから応答を受信する時間がミリ秒単位で決定されます。<br /><br /> 既定値は **100000 ミリ** (100 秒)。<br /><br /> メッセージ サイズまたはバッチ サイズが予想よりも大きい場合は、この値を増やします。<br /><br /> Windows SharePoint Services アダプターの Web サービスに対するアダプターのランタイム Web サービス呼び出しに適用されるミリ秒単位のタイムアウト値。 アダプターによって推定される平均値よりもメッセージまたはバッチ サイズが大きい場合、この値を大きくする必要があります。|  
    |クライアント OM を使用|**必要な**です。 SharePoint クライアント側オブジェクト モデル (CSOM) またはサービス側オブジェクト モデル (SSOM) のどちらを使用するかを決定します。<br /><br /> 既定値は **はい**します。 設定**はい**で SharePoint CSOM を使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターでは要件はありません。<br /><br /> 設定**いいえ**にインストールされている web サービスを含む SharePoint SSOM を使用する、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]コンピューター。<br /><br /> [付録 b: Microsoft SharePoint アダプターをインストールして](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)によって使用される SSOM と CSOM のコンポーネントに固有の情報を提供、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプター。|  
    |ターゲット フォルダーの URL|**必要な**です。 ドキュメントを格納する [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] フォルダーの URL。 SharePoint サイトへの相対パスを入力します。 たとえば、 **Shared Documents** または **Shared Documents/purchase Orders/**します。 この一覧は送信先としても使用できます たとえば、 **Lists/tasks**します。 一覧を指定すると、メッセージ本文は一覧のアイテムと共に保存されません。 メッセージから抽出される値は、SharePoint 列に昇格されます。 **注:**  SharePoint ドキュメント ライブラリまたはフォルダーの URL を名前と異なることができます。 正しい URL については、Web ブラウザーでアドレスを確認してください。|  
    |Filename|**省略可能な**です。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] のファイル名を入力します。<br /><br /> このようなファイル名を入力 **PurchaseOrder0001.xml** または式。 式には、リテラル値、マクロ、および XPATH クエリが混在します。 たとえば、入力 **PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml**します。 ファイル名を指定しないと、元のファイルの名前、オーケストレーションで指定された値、または Msg-%MessageID%.xml が使用されます。 参照してください[Windows SharePoint Services アダプター式](../core/windows-sharepoint-services-adapter-expressions.md)詳細についてはします。 **注:**  リストにメッセージを送信するときにこの Filename の値は無視され、SharePoint 列には保存されません。 代わりに、利用できる 16 列のいずれかを使用して、[タイトル] 列を更新します。 SharePoint の一覧には、[ファイル名] 列はありません。|  
    |名前空間エイリアス|**省略可能な**です。 名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧。<br /><br /> このフィールドは、[ファイル名] フィールドまたは [列値] フィールドに挿入された XPATH クエリで使用される名前空間エイリアスを定義するために使用します。 たとえば、入力 **po 'http://OrderProcess/POrder'、conf = = 'http://OrderProcess/Confirmation' xmlns =""; ipsol = '{d8217cf1-4ef7-4bb5-a30d-765ecb09e0d9}'**します。 **注:**  このプロパティは、WSS を上書きしません。ConfigNamespacesAliases メッセージ コンテキスト プロパティが、オーケストレーションによって定義されます。 その代わり、2 つの値が結合されます。|  
    |Overwrite|**必要な**です。 ファイルが存在する場合、そのファイルを上書きするかどうかを決定します。<br /><br /> 既定値は **いいえ**します。 次のオプションがあります。<br /><br /> -   **いいえ**: エラーが発生し、同じ名前のファイルが存在する場合は、メッセージを中断します。<br />-   **オーケストレーション**: 同じ名前のファイルが存在する場合は、オーケストレーションで定義されている値を使用します。<br />-   **名前を変更**: 同じ名前のファイルが存在する場合は、新しいファイルの名前を変更します。<br />-   **[はい]**: 同じ名前を持つ場合は、既存のファイルを上書きします。<br />     設定すると **はい**, 、多数の同じ名前を持つメッセージを送信するイベント ビューアーの SharePoint エラーが発生します。 このエラーによるアダプターへの影響はなく、送信できなかったメッセージは再試行されます。|  
    |SharePoint サイトの URL|**必要な**です。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サイトの完全な URL。 たとえば、http://*SharePointServer*/sites/testsite します。 **注:**  送信ポートまたは受信場所の URI は 256 文字を超えることはできません。|  
    |Microsoft Office 統合|**必要な**です。 バイナリ メッセージを使用する必要があります **いいえ** または **オプション**します。<br /><br /> 既定値は **オプション**します。 次のオプションがあります。<br /><br /> <ul><li>**いいえ**: ドキュメントを保存 **としてでは、**です。 バイナリ メッセージの場合、このオプションを使用できます。</li><li>**省略可能な**: InfoPath などの Office アプリケーションで自動的に開きますドキュメントを変更します。 処理命令がない場合は、ドキュメントが処理 **としてでは、**です。 バイナリ メッセージの場合、このオプションを使用できます。</li><li>**オーケストレーション**: は、オーケストレーションで定義されている値を使用します。</li><li>**[はい]**: InfoPath などの Office アプリケーションで自動的に開きますドキュメントを変更します。 処理の指示がない場合、メッセージは保留されます。<br /><br />     設定すると **はい**, 、次のプロパティのペアの少なくとも 1 つが必要。<br /><br /> <ul><li>*テンプレート ドキュメント ライブラリ* と *テンプレート名前空間列*</li><li>*テンプレート フォールバック ドキュメント ライブラリ* と *テンプレート フォールバック名前空間列*</li></ul></li><li>**はい (InfoPath フォーム ライブラリ)**: InfoPath などの Office アプリケーションで自動的に開きますフォーム ライブラリに InfoPath ソリューションが存在する場合、ドキュメントが変更されます。 フォーム ライブラリにソリューションがない場合、メッセージは保留されます。</li></ul>|  
    |テンプレート ドキュメント ライブラリ|**必要な*のみ*とき*テンプレート Namespace 列*が設定されます**です。 InfoPath ソリューションを格納する SharePoint ドキュメント ライブラリ。 たとえば、**マイ ソリューション**です。 アダプターが検索、*テンプレート ドキュメント ライブラリ*一致する InfoPath ソリューションです。 ソリューションが見つからない場合に、アダプター検索、 *テンプレート フォールバック ドキュメント ライブラリ*します。 **注:**  、 *テンプレート ドキュメント ライブラリ* 次が含まれる少なくとも 1 つの"1 行のテキスト"の SharePoint 列が必要です。 <ul><li>InfoPath ソリューションで開かれる XML ドキュメントの名前空間およびルート ノード</li><li>または、XML ドキュメントのルート ノード</li></ul> 詳細については、次を参照してください。[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。|  
    |テンプレート フォールバック ドキュメント ライブラリ|**必要な*のみ*とき*テンプレート フォールバック Namespace 列*が設定されます**です。 InfoPath ソリューションを格納する SharePoint ドキュメント ライブラリ。 たとえば、**テンプレート**です。<br /><br /> ソリューションが見つからない場合、*テンプレート ドキュメント ライブラリ*、アダプターはでは見えます*テンプレート フォールバック ドキュメント ライブラリ*一致する InfoPath ソリューションです。 *テンプレート フォールバック ドキュメント ライブラリ* と *テンプレート ドキュメント ライブラリ* フィールドは、2 つのセットの InfoPath ソリューションで使用できます。 すべての一般的な目的に対応する汎用の InfoPath ソリューションと、特定のパートナーで使用する特殊な InfoPath ソリューションがあります。 *テンプレート フォールバック ドキュメント ライブラリ* フィールドは、汎用的なソリューションを指す必要があり、 *テンプレート ドキュメント ライブラリ* その特定のパートナーの特殊な解決策 をポイントする必要があります。 **注:**  *テンプレート フォールバック ドキュメント ライブラリ* 次が含まれる少なくとも 1 つの"1 行のテキスト"の SharePoint 列が必要です。 <ul><li>InfoPath ソリューションで開かれる XML ドキュメントの名前空間およびルート ノード</li><li>または、XML ドキュメントのルート ノード</li></ul> 詳細については、次を参照してください。[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。|  
    |テンプレート フォールバック名前空間列|**必要な*のみ*とき*テンプレート フォールバック ドキュメント ライブラリ*が設定されます**です。 InfoPath ソリューションの名前空間を格納する SharePoint ドキュメント ライブラリ。 たとえば、 **myNamespace**します。 **注:**  このフィールドは大文字小文字を区別します。|  
    |テンプレート名前空間列|**必要な*のみ*とき*テンプレート ドキュメント ライブラリ*が設定されます**です。 SharePoint*テンプレート ドキュメント ライブラリ*InfoPath ソリューションの名前空間を格納する列。 たとえば、 **myNamespace**します。 **注:**  このフィールドは大文字小文字を区別します。|  
    |SharePoint オンライン パスワード|**省略可能な**です。 SharePoint オンライン アカウントのパスワード。|  
    |SharePoint オンライン ユーザー名|**省略可能な**です。 SharePoint オンライン アカウントのユーザー名。|  
    |[列 `n`]|**省略可能な**です。 存在する SharePoint 列、 *先のドキュメント ライブラリ*します。 指定されたまたはメッセージから抽出された値を持つこの列を更新、 *列の値* フィールドです。 **注:**  最大で 16 個の列を指定することができます。 このフィールドでは、大文字と小文字が区別されます。|  
    |[列 `n` の値]|**省略可能な**です。 このメッセージに設定する列の値を入力します。 "Purchase Order" のようなリテラル値または式を入力できます。 式には、リテラル値、マクロ、および XPATH クエリを混在させることができます。 たとえば、入力 **"%xpath=//po:poamount%"、"%sendingorchestrationid%"**します。 **注:**  最大で 16 個の列を指定することができます。|  
  
5.  クリックして **OK** 設定を保存します。  
  
6.  送信ポートのその他の構成オプションは次のとおりです。  
  
    1.  [送信ポートに対してトランスポートの詳細オプションを構成する方法](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
    2.  [送信ポートに対してバックアップ トランスポートのオプションを構成する方法](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  
  
    3.  [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
    4.  [送信ポートのフィルターを構成する方法](../core/how-to-configure-filters-for-a-send-port.md)  
  
    5.  [送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
    6.  [送信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-send-port.md)  
  
##  <a name="BKMK_DynamicSend"></a> 動的送信ポートを作成します。  
 動的送信ポートを作成するときは、送信ハンドラーが各アダプターに対して構成可能になります。 1 つの動的送信ポートは複数のアダプターで使用できます。 参照してください[動的送信ポート ハンドラーは構成可能](../core/dynamic-send-port-handler-is-configurable.md)手順については、動的送信ポート ハンドラーを構成します。  
  
1.  **BizTalk Server 管理コンソール**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーション。  
  
2.  右クリックし **送信ポート**, をクリックして **新規**, 、にして **動的な一方向送信ポート** または **動的な送信請求-応答送信ポート**  
  
3.  **プロパティ**, 、入力、 **名前** と **パイプライン** プロパティ  
  
     クリックして **構成**します。  
  
4.  **送信ハンドラーの構成** ウィンドウで、選択、 **送信ハンドラー** 、個別のアダプターです。 既定の送信ハンドラーは **BizTalkServerApplication**します。 新しい送信ハンドラーを追加する手順についてを参照してください [をアダプター ハンドラーを作成する方法](http://go.microsoft.com/fwlink/p/?LinkId=263646)します。  
  
     別のホストを使用する理由は、次のように多くあります。  
  
    -   **32 ビット要件**: 一部のアダプターは、FTP、POP3 アダプターのように、32 ビットのホストを必要とします。 すべての 32 ビット アダプターまたは個別の 32 ビット アダプターを独自のホストにグループ化することができます。  
  
         [BizTalk Server の 64 ビットのサポート](../core/biztalk-server-64-bit-support2.md)  
  
    -   **目的別のホスト**: 送信するためのホスト、受信用ホスト、処理のオーケストレーションのホストおよび追跡用のホストを作成します。  
  
    -   **別のホスト設定**: 多くの設定は、ホスト レベルで実装されます。 その結果、各ホストに対して異なる制限設定を構成可能です。 たとえば、HostA で制限を無効にできます。 HostB で各イベントを追跡します。 HostC の .NET CLR 設定を変更します。 HostD のメモリ使用量を増やします。  
  
    -   **セキュリティ**: ホスト レベルでセキュリティを実装します。 各ホストは独自の Windows アカウントで実行されます。 たとえば、HostA は FILE アダプターを使用してファイル共有にアクセスします。 HostA に、ファイル共有へのユーザー アカウント アクセス許可を与えます。 HostB は IIS サーバーでホストされた Web サービスを使用します。 HostB に、Web サービスへのユーザー アカウント許可を与えます。 これにより、その他のホスト アカウントが、アクセスする必要がないエンティティにアクセスできないようにもなります。  
  
    -   **個別のアダプター**: たとえば、複数のアイテムがある (受信場所と送信ポート) HTTP アダプターを使用します。 すべてを独自のホストで HTTP アダプターに関連付ける場合などです。  
  
    -   **個別のオーケストレーション**: 個別のオーケストレーションは、独自のホストにすることができます。 たとえば、オーケストレーションで多くのメモリまたは CPU を使用する場合は、そのオーケストレーションを独自のホストに配置します。  
  
     [BizTalk Server パフォーマンス最適化ガイド](http://msdn.microsoft.com/library/dn775063\(v=bts.10\).aspx) と [を維持し、BizTalk Server データベースのトラブルシューティングを行う方法](http://support.microsoft.com/kb/952555) パフォーマンスに関する推奨事項を提供します。  
  
5.  クリックして **OK** 設定を保存します。  
  
6.  送信ポートのその他の構成オプションは次のとおりです。  
  
    1.  [送信ポートに対してトランスポートの詳細オプションを構成する方法](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
    2.  [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
    3.  [送信ポートのフィルターを構成する方法](../core/how-to-configure-filters-for-a-send-port.md)  
  
    4.  [送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
    5.  [送信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-send-port.md)  
  
7.  クリックして **OK** 設定を保存します。  
  
 送信ポートに関する追加情報  
  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)  
  
 [送信ポート グループの作成および構成](../core/creating-and-configuring-send-port-groups.md)  
  
## <a name="see-also"></a>参照  
 [SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-sharepoint-services-adapter.md)   
 [SharePoint を構成する受信場所のサービス](../core/configure-sharepoint-services-receive-location.md)   
 [CSOM: SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)