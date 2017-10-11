---
title: "SharePoint を構成するサービスの受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afed0e4-0f72-4df4-a2cb-d999c6fbbc86
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 807f13611b7e8977e0d5067787717427efc4bed2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-sharepoint-services-receive-location"></a>SharePoint Services 受信場所の構成
このトピックでは、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 受信場所の作成手順を示します。  
  
## <a name="create-a-receive-location"></a>受信場所の作成  
 受信場所を作成する際、受信場所は、トランスポートの種類に関連付けられた既定の受信ハンドラーを使用します。 使用する場合、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプター、既定の受信ハンドラーは**BizTalkServerApplication**です。 新しい受信ハンドラーを追加する手順についてを参照してください[アダプター ハンドラーを作成する方法](http://go.microsoft.com/fwlink/p/?LinkId=263646)です。  
  
 受信場所の作成:  
  
1.  **BizTalk Server 管理コンソール**コンソールで、  **BizTalk グループ [*GroupName*] * *、展開**アプリケーション**、順に展開受信場所を格納するアプリケーション。  
  
2.  作成、**一方向受信ポート**です。 [受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)手順について説明します。  
  
    > [!IMPORTANT]
    >  A**要求-応答受信場所**で構成することはありません、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプター。  
  
     受信ポートのその他の構成オプションは次のとおりです。  
  
     [受信ポートに受信場所を追加する方法](../core/how-to-add-a-receive-location-to-a-receive-port.md): 次の手順で、受信場所を追加します。  
  
     [受信マップを構成する方法、受信ポート](../core/how-to-configure-inbound-maps-for-a-receive-port.md)  
  
     [追跡を構成する方法、受信ポート](../core/how-to-configure-tracking-for-a-receive-port.md)  
  
3.  をクリックして**OK**設定を保存します。  
  
4.  右クリック**受信場所**をクリックして**新規**、順にクリック**一方向の受信場所**です。  
  
    > [!IMPORTANT]
    >  A**要求-応答受信場所**で構成することはありません、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプター。  
  
5.  受信ポートを選択し、クリックして**OK**です。  
  
6.  **プロパティ**、入力、**名前**と**パイプライン**プロパティです。 **型**ドロップダウン リストをクリックして**Windows SharePoint Services**を選択し、**受信ハンドラー**プロパティです。  
  
7.  をクリックして**構成**です。 **プロパティ**次を構成します。  
  
    |||  
    |-|-|  
    |アダプター Web サービス ポート|**必要な**します。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプター Web サービスをホストしている IIS Web サイト上で構成されるポート。<br /><br /> 既定値はポート**80**、これは、標準の HTTP ポート。 80 以外のポートを使用するときは、この値を更新します。|  
    |Timeout|**必要な**します。 この値により、アダプターが Web サービスから応答を受信する時間がミリ秒単位で決定されます。<br /><br /> 既定値は**100000 ミリ**(100 秒)。<br /><br /> メッセージ サイズまたはバッチ サイズが予想よりも大きい場合は、この値を増やします。|  
    |クライアント OM を使用|**必要な**します。 SharePoint クライアント側オブジェクト モデル (CSOM) またはサービス側オブジェクト モデル (SSOM) のどちらを使用するかを決定します。<br /><br /> 既定値は**はい**です。 設定**はい**で SharePoint CSOM を使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターでは要件はありません。<br /><br /> 設定**いいえ**にインストールされている web サービスを含む SharePoint SSOM を使用する、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]コンピューター。<br /><br /> [付録 b: Microsoft SharePoint アダプターをインストールして](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)によって使用される SSOM と CSOM のコンポーネントに固有の情報を提供、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプター。|  
    |アーカイブ ファイル名|**省略可能な**します。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サービスは、SharePoint ライブラリからドキュメントをアーカイブすることができます。 アーカイブ ファイルの名前を入力します。<br /><br /> 同様に、ファイル名を入力**PurchaseOrder0001.xml**または式。 式には、リテラル値、マクロ、および XPATH クエリが混在します。 たとえば、"PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml"です。 ファイル名が指定されていない場合、ソース ファイルのファイル名が使用されます。 参照してください[Windows SharePoint Services アダプター式](../core/windows-sharepoint-services-adapter-expressions.md)詳細についてはします。 **注:** "%sendingorchestrationid%"と"%sendingorchestrationtype%"マクロは、このフィールドではサポートされません。|  
    |アーカイブ先 URL|**省略可能な**します。 アーカイブしたドキュメントを格納する [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] フォルダーの URL。 SharePoint サイトへの相対パスを入力します。 たとえば、**アーカイブ**または**/shared Documents/processed Orders/**です。 アーカイブ場所を指定しない場合、アダプターによって処理された後にドキュメントが削除されます。 **注:** SharePoint ドキュメント ライブラリまたはフォルダーの URL をその名前と異なることができます。 正しい URL については、Web ブラウザーでアドレスを確認してください。|  
    |アーカイブの上書き|**必要な**します。 既存のファイルを上書きするよう指定します。<br /><br /> 既定値は**いいえ**、アーカイブと同じ名前のファイルが存在する場合は、アーカイブに失敗します。 このシナリオでは、ファイルがチェックアウトされ、手動でアーカイブする必要があります。 **注:**アーカイブ ファイルは、マクロでアーカイブ ファイル名の値を使用するときに、ファイル名は一意です。 たとえばなどのアーカイブ ファイル名を使用 **PO-%MessageID%.xml または PO-%XPATH=//ns0:PurchaseOrder/ns0:*ID*%.xml**、ID は、一意の注文書の注文 id です。|  
    |バッチ サイズ|**必要な**します。 Web サービスでバッチとして処理できるドキュメント数の上限。 処理されるバッチには、定義したバッチ サイズより少ない数のメッセージを含めることができます。 それより多くのメッセージは格納しません。<br /><br /> 既定値は**20**必要がありますの値には、少なくともと**1**です。|  
    |エラーのしきい値|**必要な**します。 受信場所が無効になるまでにアダプターで連続して発生するポーリング障害の最大数。<br /><br /> 既定値は**10**です。 設定を無効になっている受信場所を停止する**0**します。|  
    |名前空間エイリアス|**省略可能な**します。 名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧。<br /><br /> このフィールドを使用して、上記の [アーカイブ ファイル名] フィールドに設定された XPATH クエリで使用される、名前空間エイリアスを定義します。 たとえば、入力**po 'http://OrderProcess/POrder'、conf = = 'http://OrderProcess/Confirmation' ipsol = '{d8217cf1-4ef7-4bb5-a30d-765ecb09e0d9}'**です。|  
    |ポーリング間隔|**必要な**します。 新しいメッセージを待つアダプターによって実行されるクエリの間隔を秒で指定します。<br /><br /> 既定値は**60**必要がありますの値には、少なくともと**1**です。 **注:**アダプターのスループットと応答時間を向上させるのに低い値を入力します。|  
    |SharePoint サイトの URL|**省略可能な**します。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サイトの完全な URL。 たとえば、http:// *SharePointServer*  /サイト/です。 **注:** A の送信ポートまたは受信場所 URI は 256 文字を超えることはできません。|  
    |基になるドキュメント ライブラリの URL|**省略可能な**します。 ドキュメントが取得される [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] ドキュメント ライブラリの URL 相対パス。 たとえば、 **/Shared Documents/**または**/new Purchase Orders/**です。 **注:** SharePoint ドキュメント ライブラリをその名前と異なることができます。 正しい URL については、Web ブラウザーでアドレスを確認してください。|  
    |ビュー名|**省略可能な**します。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプターによって処理されたドキュメントをフィルター処理に使用されるビューです。 たとえば、 **Approved Orders**です。<br /><br /> ソース ドキュメント ライブラリの既存のドキュメントをすべて処理する場合、このフィールドを空のままにします。 ビュー内のフォルダーとそれらのフォルダー内のメッセージは、アダプターによって処理されません。 サブフォルダーのドキュメントを含むフラットな構造ですべてのドキュメントを表示するフラット ビューを作成します。|  
    |Microsoft Office 統合|**必要な**します。 バイナリ メッセージについては、[いいえ] または [省略可能] を選択する必要があります。<br /><br /> 既定値は**オプション**です。<br /><br /> 次のオプションがあります。<br /><br /> -   **いいえ**:「現状有姿のドキュメントを処理します。 バイナリ メッセージの場合、このオプションを使用できます。<br />-   **省略可能な**: InfoPath 処理命令を削除しようとしています。 処理命令が削除されない場合、ドキュメントは "そのまま" 処理されます。 バイナリ メッセージの場合、このオプションを使用できます。<br />-   **[はい]**: 削除の InfoPath 処理命令します。 エラーが発生すると、メッセージが無視されます。|  
    |SharePoint オンライン パスワード|**省略可能な**します。 SharePoint オンライン アカウントのパスワード。|  
    |SharePoint オンライン ユーザー名|**省略可能な**します。 SharePoint オンライン アカウントのユーザー名。|  
  
8.  をクリックして**OK**設定を保存します。  
  
9. 受信場所のその他の構成オプションは次のとおりです。  
  
     [スケジュールを構成する方法、受信場所](../core/how-to-configure-scheduling-for-a-receive-location.md)  
  
10. をクリックして**OK**設定を保存します。  
  
 受信ポートおよび受信場所に関するその他のトピック:  
  
 [受信ポートの管理](../core/managing-receive-ports.md)  
  
 [受信場所の管理](../core/managing-receive-locations.md)  
  
 次に、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 送信ポートを作成します。  
  
 [SharePoint Services 送信ポートを構成します。](../core/configure-sharepoint-services-send-port.md)  
  
## <a name="see-also"></a>参照  
 [SharePoint Services 送信ポートを構成します。](../core/configure-sharepoint-services-send-port.md)   
 [SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-sharepoint-services-adapter.md)   
 [SharePoint Services アダプターの CSOM:](../core/csom-sharepoint-services-adapter.md)