---
title: Windows Sharepoint Services アダプター構成プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, properties
- receive locations, adapters
- Windows SharePoint Services adapters, code sample
- Windows SharePoint Services adapters, send ports
- Windows SharePoint Services adapters, receive locations
- Windows SharePoint Services adapters
- send ports, adapters
ms.assetid: 20b08959-75d3-4613-9cea-582ac2813415
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb08d32ad85be68922a2ddf0b6fe4ac0d8c915e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975152"
---
# <a name="windows-sharepoint-services-adapter-configuration-properties"></a>Windows SharePoint Services アダプターの構成プロパティ
次の表に、Windows Sharepoint Services アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Windows SharePoint Services Web サイトの完全な URL を指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|WssLocation|VT_BSTR|ドキュメントの取得元となる、SharePoint サイトと相対的な Windows SharePoint Services ドキュメント ライブラリの URL を指定します。|メッセージは、SharePoint の一覧またはフォルダーからは取得できません。|SharePoint ドキュメント ライブラリは、そのアイテム自体の名前とは異なる場合があります。 正しい URL を探索する Internet Explorer のアドレス バーを確認してください。|  
|ViewName|VT_BSTR|アダプターによって処理されるドキュメントをフィルター処理するために使用される Windows SharePoint Services ビューを指定します。|なし|フラット ビューのすべてのメッセージが処理されます。|  
|ArchiveLocation|VT_BSTR|処理されたファイルがアーカイブされて、SharePoint サイトに関連して、Windows SharePoint Services フォルダーの URL を指定します。|なし|SharePoint ドキュメント ライブラリやフォルダの URL は、そのアイテム自体の名前とは異なる場合があります。 正しい URL を探索する Internet Explorer のアドレス バーを確認してください。|  
|NamespaceAliases|VT_BSTR|名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧を指定します。|なし|なし|  
|ArchiveFileName|VT_BSTR|アーカイブ済みファイルの Windows SharePoint Services ファイル名を指定します。|このフィールドでは、"%SendingOrchestrationID%" マクロと "%SendingOrchestrationType%" マクロはサポートされていません。|なし|  
|Overwrite|VT_BSTR|アーカイブの既存のファイルを上書きするかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|ErrorThreshold|VT_BSTR|受信場所を無効にするための上限として、アダプターで連続して発生するポーリング障害の最大数を指定します。|有効な値は 0 ~ 2,147, 483,647 です。|このプロパティを 0 に設定すると、受信場所は無効になりません。<br /><br /> 既定値は 10 です。|  
|PollingInterval|VT_BSTR|処理する新しいメッセージがあるかどうかを確認するために、アダプターによって実行される 2 つの連続したクエリ間の秒単位の時間間隔を指定します。|有効な値は 1 ~ 2,147, 483,647 です。|小さい値を指定すると、アダプタのスループットおよび応答時間が改善されます。<br /><br /> 既定値は 60 です。|  
|BatchSize|VT_BSTR|Windows SharePoint Services メッセージ アダプター Web サービスでバッチとして処理するドキュメントの最大数を指定します。|有効な値は 1 ~ 2,147, 483,647 です。|処理されるバッチには、定義されたバッチ サイズ未満のメッセージを格納できますが、そのサイズを超えるメッセージは格納できません。<br /><br /> 既定値は 20 です。|  
|OfficeIntegration|VT_BSTR|Office 統合のレベルを指定します。|有効な値は、<br /><br /> -   **省略可能な**- 可能であれば InfoPath 処理命令を削除しようとしています。 または、として処理するができない場合。<br />-   **いいえ**-有"ドキュメントの処理。<br />-   **[はい]** - InfoPath 処理命令を削除するか、エラーが発生した場合、メッセージをスキップします。|既定値は optional です。|  
|Timeout|VT_BSTR|アダプター ランタイム Web サービスへの呼び出し、Windows SharePoint Services アダプター Web サービスのミリ秒単位のタイムアウトを指定します。|有効な値は、1000 ~ 2,147, 483,647 です。|既定値は、100000 です。|  
|AdapterWSPort|VT_BSTR|Windows SharePoint Services アダプターの Web サービスがインストールされる IIS Web サイトの HTTP ポートを指定します。|なし|既定値は 80 です。|  
|uri|VT_BSTR|Windows SharePoint Services ドキュメント ライブラリへの完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><ReceiveLocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BTS2006/sites/BASSite/</SiteUrl><WssLocation>Shared Docs</WssLocation><ViewName>Approved</ViewName><ArchiveLocation>Archive</ArchiveLocation><NamespaceAliases>po='http://POProcess/POrder'</NamespaceAliases><ArchiveFileName>PurchaseOrder0001.xml</ArchiveFileName><Overwrite>no</Overwrite><ErrorThreshold>10</ErrorThreshold><PollingInterval>60</PollingInterval><BatchSize>20</BatchSize><OfficeIntegration>optional</OfficeIntegration><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://bts2006:80/sites/BASSite/Shared+Docs?ViewName=Approved</uri></ReceiveLocation></AdapterConfig></CustomProps>  
```  
  
 次の表に、Windows Sharepoint Services アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Windows SharePoint Services Web サイトの完全な URL を指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|WssLocation|VT_BSTR|Windows SharePoint Services 送信先フォルダーの URL を SharePoint サイトからの相対パスで指定します。|なし|SharePoint ドキュメント ライブラリ、一覧、またはフォルダの URL は、アイテムの名前と異なる場合があります。 正しい URL を参照するには、Internet Explorer のアドレス バーを確認してください。|  
|Overwrite|VT_BSTR|既存のファイルを上書きするかどうかを指定します。|有効な値は、<br /><br /> -なし<br />オーケストレーション<br />-名前の変更<br />-[はい]|既定値はありません。|  
|NamespaceAliases|VT_BSTR|名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧を指定します。|なし|フィールドに設定された XPATH クエリで使用される名前空間エイリアスを定義します。<br /><br /> このプロパティは、オーケストレーションによって定義される WSS.ConfigNamespacesAliases メッセージ コンテキスト プロパティを上書きしません。 代わりに、2 つの値が結合されます。|  
|FileName|VT_BSTR|Windows SharePoint Services のファイル名を指定します。|なし|メッセージを一覧に送信する際、"ファイル名" プロパティに指定された値は無視され、SharePoint 列には保存されません。 SharePoint の一覧には、[ファイル名] 列はありません。 代わりに、利用できる 16 列のいずれかを使用して [タイトル] 列を更新します。|  
|OfficeIntegration|VT_BSTR|ドキュメントを変更して InfoPath などの Office アプリケーションでドキュメントが自動的に開くようにするか、または InfoPath ソリューションが見つからない場合はドキュメントをそのまま保存するように指定します。|有効な値は、<br /><br /> -なし<br />-省略可能な<br />オーケストレーション<br />-[はい]<br />-yesformlibrary|既定値は optional です。|  
|TemplatesDocLib|VT_BSTR|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を指定します。|TemplatesNamespaceCol プロパティに値が含まれる場合は、このプロパティに値を指定する必要があります。|ドキュメント ライブラリでは、型が "1 行のテキスト" の SharePoint 列が少なくとも 1 列あり、この列にはこの InfoPath ソリューションで開くことができる XML ドキュメントの名前空間とルート ノード、または単にルート ノードが設定されている必要があります。|  
|TemplatesNamespaceCol|VT_BSTR|InfoPath ソリューションの格納先となるテンプレート フォールバック ドキュメント ライブラリの SharePoint 列の名前を指定します。|TemplatesDocLib プロパティに値が含まれる場合は、このプロパティに値を指定する必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|CustomTemplatesDocLib|VT_BSTR|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を指定します。|CustomTemplatesNamespaceCol プロパティに値が含まれる場合は、このプロパティに値を指定する必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|CustomTemplatesNamespaceCol|VT_BSTR|InfoPath ソリューションの格納先となるテンプレート ドキュメント ライブラリの SharePoint 列の名前を指定します。|CustomTemplatesDocLib プロパティに値が含まれる場合は、このプロパティに値を指定する必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|PropertyName(n)|VT_BSTR|送信先ドキュメント ライブラリに存在する Windows SharePoint Services 列の名前を指定します。|このフィールドでは、大文字と小文字が区別されます。|16 列まで指定できます。|  
|PropertySource(n)|VT_BSTR|このメッセージに設定する列の値を指定します。|なし|最大 16 列の値を指定することができます。|  
|Timeout|VT_BSTR|Windows SharePoint Services アダプターの Web サービスに対するアダプターのランタイム Web サービス呼び出しに適用されるミリ秒単位のタイムアウト値を指定します。|有効な値は、1000 ~ 2,147, 483,647 です。|既定値は、100000 です。|  
|AdapterWSPort|VT_BSTR|Windows SharePoint Services アダプターの Web サービスがインストールされる IIS Web サイトの HTTP ポートを指定します。|なし|既定値は 80 です。|  
|uri|VT_BSTR|Windows SharePoint Services 送信先フォルダーの URL への完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
> [!NOTE]
>  PropertyName2 および PropertySource2 から PropertyName16 および PropertySource16 までの定義は、この文字列から省略されました。  
  
```  
<CustomProps><AdapterConfig vt="8"><SendPort xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BizTalkServer/sites/BASSite/</SiteUrl><WssLocation>Shared Documents/Purchase Orders</WssLocation><Overwrite>yes</Overwrite><NamespaceAliases>po='http://OrderProcess/POrder'</NamespaceAliases><FileName>PurchaseOrder0001.xml</FileName><OfficeIntegration>yesformlibrary</OfficeIntegration><TemplatesDocLib>Templates</TemplatesDocLib><TemplatesNamespaceCol>NamespaceFallback</TemplatesNamespaceCol><CustomTemplatesDocLib>Shared Documents</CustomTemplatesDocLib><CustomTemplatesNamespaceCol>Namespace</CustomTemplatesNamespaceCol><PropertyName1>Column1</PropertyName1><PropertySource1>Column1 Value</PropertySource1><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://biztalkserver:80/sites/BASSite/Shared%20Documents/Purchase%20Orders</uri></SendPort></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前/値ペア必要がありますすべてに格納される、 \<AdapterConfig\>要素。 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。