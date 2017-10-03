---
title: "サービスの受信場所を Windows SharePoint を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], receive locations
- Windows SharePoint Services adapters, receive locations
ms.assetid: 5db3d5cf-4a77-4985-bd03-307c520247ec
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22a23f97634eaba9dccccd099f7c39ba6af75d67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-windows-sharepoint-services-receive-location"></a>Windows SharePoint Services の受信場所を構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して Windows SharePoint Services の受信場所を作成および構成する方法について説明します。  
  
### <a name="to-create-and-configure-a-windows-sharepoint-services-receive-location"></a>Windows SharePoint Services の受信場所を作成および構成するには  
  
1.  受信ポートが正しく構成されていることを確認してください。 作成して、受信ポートを構成する方法については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
2.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ [グループ名]**、展開**アプリケーション**、し、受信場所を作成するアプリケーションを展開します。  
  
3.  右クリック**受信場所**をクリックして**新規**、順にクリック**一方向の受信場所**です。  
  
4.  この受信場所をクリックし、受信ポートを選択して**OK**です。  
  
5.  **受信場所のプロパティ**ダイアログ ボックスで、**トランスポート**で、**型**ドロップダウン ボックスで、 **Windows SharePoint Services**.  
  
6.  をクリックして**構成**です。  
  
7.  **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |アダプター Web サービス ポート|Windows SharePoint Services アダプタの Web サービスがインストールされる IIS Web サイトの HTTP ポート。 既定では、これは、ポート 80 で構成されている既定の Web サイトです。 既定の Web サイト以外の IIS Web サイトに Windows SharePoint Services Web サービスを構成した場合は、この値を更新する必要があります。|  
    |Timeout|Windows SharePoint Services アダプターの Web サービスに対するアダプターのランタイム Web サービス呼び出しに適用されるミリ秒単位のタイムアウト値。 アダプターによって推定される平均値よりもメッセージまたはバッチ サイズが大きい場合、この値を大きくする必要があります。|  
    |アーカイブ ファイル名|(省略可)。アーカイブ済みファイルの Windows SharePoint Services ファイル名。 "PurchaseOrder0001.xml" のようなリテラル値または式を入力できます。 式には、リテラル値、マクロ、および XPATH クエリを混在させることができます。 たとえば、"PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml"です。 ファイル名を指定しなかった場合は、ソース ファイルのファイル名が使用されます。 式の詳細については、次を参照してください。 [Windows SharePoint Services アダプター式](../core/windows-sharepoint-services-adapter-expressions.md)です。 **注:** "%sendingorchestrationid%"と"%sendingorchestrationtype%"マクロは、このフィールドではサポートされません。|  
    |アーカイブ先 URL|処理されたファイルがアーカイブされる、SharePoint サイトと相対的な Windows SharePoint Services フォルダの URL。 たとえば、"Archive" または "/Shared Documents/Processed Orders/" などです。 アーカイブ場所を指定しなかった場合、ドキュメントは、アダプタによって処理された後に削除されます。 **注:**ことがあります SharePoint ドキュメント ライブラリまたはフォルダーの URL とは異なるその項目の名前。 正しい URL を探索する Internet Explorer のアドレス バーを確認してください。|  
    |アーカイブの上書き|アーカイブの既存のファイルを上書きするかどうかを決定します。 [はい] を選択すると、既存のファイルが上書きされます。 [いいえ] を選択すると、同じ名前のファイルがアーカイブに存在する場合、アーカイブに失敗します。 この場合、ファイルはチェックアウトされたままになるため、手動でそのファイルをアーカイブする必要があります。 **注:**ファイルの名前を一意にするためにマクロでアーカイブ ファイル名の値を使用するファイルをアーカイブする際にお勧めします。 このため、PO-%MessageID%.xml や PO-%XPATH=//ns0:PurchaseOrder/ns0:ID%.xml などのアーカイブ ファイル名を使用できます。ID は注文書の一意な ID です。|  
    |バッチ サイズ|Windows SharePoint Services メッセージ アダプタ Web サービスでバッチとして処理するドキュメントの最大数。 処理されるバッチには、定義されたバッチ サイズ未満のメッセージを格納できますが、そのサイズを超えるメッセージは格納できません。|  
    |エラーのしきい値|受信場所が無効になるまでにアダプタで連続して発生するポーリング障害の最大数。 このフィールドを 0 に設定すると、受信場所は無効になりません。|  
    |名前空間エイリアス|(省略可能) 名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧。 このフィールドを使用して、[アーカイブ ファイル名] フィールドに設定された XPATH クエリで使用される、名前空間エイリアスを定義します。 たとえば、po='http://OrderProcess/POrder'、conf='http://OrderProcess/Confirmation'、ipsol='{D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}' などです。|  
    |ポーリング間隔|処理する新しいメッセージがあるかどうかを確認するために、アダプタによって実行される 2 つの連続したクエリ間の秒単位の時間間隔。 **注:**アダプターのスループットと応答時間が短縮下限値を指定します。|  
    |SharePoint サイトの URL|Windows SharePoint Services Web サイトの完全な URL。 たとえば、http://BizTalkServer/sites/TestSite などです。 **注:**の URI を送信ポートまたは受信場所は、256 文字を超えることはできません。|  
    |基になるドキュメント ライブラリの URL|ドキュメントの取得元となる、SharePoint サイトと相対的な Windows SharePoint Services ドキュメント ライブラリの URL。 たとえば、/Shared Documents/ や /New Purchase Orders/ などです。 **注:** SharePoint リストからメッセージを受信することはできません。 SharePoint フォルダからのメッセージを受信するには、すべてのフォルダ内のメッセージを表示するビューを使用する必要があります。 設定するこれを行うには、**フォルダー**プロパティの値を**フォルダーなしのすべてのドキュメントを表示する**ビューを作成するときにします。 **注:** SharePoint ドキュメント ライブラリがその項目の名前と異なる場合があります。 正しい URL を探索する Internet Explorer のアドレス バーを確認してください。|  
    |ビュー名|アダプタによって処理されるドキュメントをフィルタ処理するために使用される Windows SharePoint Services ビュー。 たとえば、"Approved Orders" などです。 このフィールドは元のドキュメント ライブラリ内の既存のすべてのドキュメントを処理する場合は空のままにします。 ビューに表示されるフォルダとそれらのフォルダに含まれるメッセージは、アダプタによって処理されません。 サブフォルダのドキュメントを含むフラットな構造ですべてのドキュメントを表示するフラット ビューを作成できます。 **注:**フラット ビューのすべてのメッセージが処理されます。|  
    |Microsoft Office 統合|[省略可能] を選択すると、InfoPath 処理命令が削除可能な場合は削除され、削除できない場合 (バイナリ ドキュメントの場合など) はそのまま処理されます。 [はい] を選択すると、InfoPath 処理命令が削除され、エラーが発生した場合はメッセージがスキップされます。 [いいえ] を選択すると、ドキュメントが "そのまま" 処理されます。 バイナリ メッセージについては、[いいえ] または [省略可能] を選択する必要があります。|  
  
8.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティのリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Windows SharePoint Services 列の型のサポート](../core/supported-windows-sharepoint-services-column-types.md)