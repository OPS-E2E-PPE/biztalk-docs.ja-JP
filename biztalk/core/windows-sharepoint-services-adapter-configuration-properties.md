---
title: Windows Sharepoint Services アダプター構成プロパティ |Microsoft Docs
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
ms.openlocfilehash: dd4d9afc512b99815ca5a7ea862ac45868e99edf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240316"
---
# <a name="windows-sharepoint-services-adapter-configuration-properties"></a>Windows Sharepoint Services アダプター構成プロパティ
次の表の Windows Sharepoint Services アダプターを設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Windows SharePoint Services Web サイトの完全な URL を指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|WssLocation|VT_BSTR|ドキュメントの取得、SharePoint サイトと相対的な Windows SharePoint Services ドキュメント ライブラリの URL を指定します。|SharePoint リストまたはフォルダーからメッセージを受信できません。|場合があります SharePoint ドキュメント ライブラリは、その項目の名前と異なる。 正しい URL を検出する Internet Explorer のアドレス バーを確認します。|  
|ビュー名|VT_BSTR|ビューは、アダプターによって処理されたドキュメントをフィルター処理に使用する Windows SharePoint Services を指定します。|なし|すべてのメッセージをフラット ビューでは処理されます。|  
|ArchiveLocation|VT_BSTR|処理されたファイルがアーカイブは、SharePoint サイトと相対的な Windows SharePoint Services フォルダの URL を指定します。|なし|場合によって、SharePoint ドキュメント ライブラリまたはフォルダーの URL は、その項目の名前と異なります。 正しい URL を検出する Internet Explorer のアドレス バーを確認します。|  
|NamespaceAliases|VT_BSTR|コンマまたはセミコロン区切りのリストの名前空間エイリアスの定義を指定します。|なし|なし|  
|ArchiveFileName|VT_BSTR|アーカイブ ファイルの Windows SharePoint Services ファイル名を指定します。|このフィールドでは、"%sendingorchestrationid%"と"%sendingorchestrationtype%"マクロはサポートされていません。|なし|  
|Overwrite|VT_BSTR|アーカイブの既存のファイルを上書きするかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|ErrorThreshold|VT_BSTR|受信場所が無効になるまでに、アダプターで発生した連続するポーリング障害の最大数を指定します。|有効な値は 0 ~ 2,147, 483,647 です。|0 にない受信場所を無効にするためにこのプロパティを設定します。<br /><br /> 既定値は 10 です。|  
|PollingInterval|VT_BSTR|新しいメッセージが処理に使用できるアダプターによって実行される 2 つの連続したクエリ間の秒単位の時間間隔を指定します。|有効な値は 1 ~ 2,147, 483,647 です。|下限値を指定するには、アダプターのスループットと応答時間が向上します。<br /><br /> 既定値は 60 です。|  
|BatchSize|VT_BSTR|バッチとして、Windows SharePoint Services メッセージ アダプター Web サービスを処理するドキュメントの最大数を指定します。|有効な値は 1 ~ 2,147, 483,647 です。|処理されるバッチには、定義されたバッチ サイズ未満のメッセージを格納できますが、そのサイズを超えるメッセージは格納できません。<br /><br /> 既定値は、20 です。|  
|OfficeIntegration|VT_BSTR|Office 統合のレベルを指定します。|有効な値は、<br /><br /> -   **省略可能な**- InfoPath 処理命令が可能であれば削除しようとしています。 または、として処理ができない場合。<br />-   **いいえ**-"です」とドキュメントの処理。<br />-   **[はい]** - InfoPath 処理命令を削除するか、エラーが発生した場合、メッセージをスキップします。|既定値は省略可能です。|  
|Timeout|VT_BSTR|Windows SharePoint Services アダプター Web サービスに対するアダプターのランタイム Web サービス呼び出しのミリ秒単位のタイムアウトを指定します。|有効な値は、1000 ~ 2,147, 483,647 です。|既定値は 100000 です。|  
|AdapterWSPort|VT_BSTR|Windows SharePoint Services アダプター Web サービスがインストールされている IIS Web サイトの HTTP ポートを指定します。|なし|既定値は 80 です。|  
|Uri|VT_BSTR|Windows SharePoint Services ドキュメント ライブラリへの完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><ReceiveLocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BTS2006/sites/BASSite/</SiteUrl><WssLocation>Shared Docs</WssLocation><ViewName>Approved</ViewName><ArchiveLocation>Archive</ArchiveLocation><NamespaceAliases>po='http://POProcess/POrder'</NamespaceAliases><ArchiveFileName>PurchaseOrder0001.xml</ArchiveFileName><Overwrite>no</Overwrite><ErrorThreshold>10</ErrorThreshold><PollingInterval>60</PollingInterval><BatchSize>20</BatchSize><OfficeIntegration>optional</OfficeIntegration><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://bts2006:80/sites/BASSite/Shared+Docs?ViewName=Approved</uri></ReceiveLocation></AdapterConfig></CustomProps>  
```  
  
 次の表では、Windows Sharepoint Services アダプターの送信ポートを設定できる構成プロパティを示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|Windows SharePoint Services Web サイトの完全な URL を指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|WssLocation|VT_BSTR|Windows SharePoint Services 送信先フォルダー URL、SharePoint サイトと相対的に指定します。|なし|場合があります SharePoint ドキュメント ライブラリ、リスト、またはフォルダーの URL は、その項目の名前と異なる。 正しい URL を参照するには、Internet Explorer のアドレス バーを確認してください。|  
|Overwrite|VT_BSTR|既存のファイルを上書きするかどうかを指定します。|有効な値は、<br /><br /> -なし<br />オーケストレーション<br />-名前の変更<br />-[はい]|既定値はありません。|  
|NamespaceAliases|VT_BSTR|コンマまたはセミコロン区切りのリストの名前空間エイリアスの定義を指定します。|なし|このフィールドを使用すると、フィールドに設定された XPATH クエリで使用される名前空間エイリアスを定義します。<br /><br /> このプロパティは、WSS を上書きしません。ConfigNamespacesAliases メッセージ コンテキスト プロパティがオーケストレーションによって定義されます。 代わりに、2 つの値が結合されます。|  
|FileName|VT_BSTR|Windows SharePoint Services ファイル名を指定します。|なし|リストにメッセージを送信するときに、Filename プロパティで指定された値は無視され、SharePoint 列には保存されません。 SharePoint の一覧には、[ファイル名] 列はありません。 代わりに、利用できる 16 列のいずれかを使用して、タイトル列を更新します。|  
|OfficeIntegration|VT_BSTR|InfoPath ソリューションが検出されないかどうかは、ドキュメントを保存するか、ドキュメントを変更して InfoPath などの Office アプリケーションで自動的に開くように指定します。|有効な値は、<br /><br /> -なし<br />-オプション<br />オーケストレーション<br />-[はい]<br />-yesformlibrary|既定値は省略可能です。|  
|TemplatesDocLib|VT_BSTR|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を指定します。|TemplatesNamespaceCol プロパティに値が含まれている場合、このプロパティは、値を含める必要があります。|ドキュメント ライブラリの種類の 1 行の名前空間が設定されているテキストとこの InfoPath ソリューションで開くことができる XML ドキュメントのルート ノード、または単にルート ノードの少なくとも 1 つの SharePoint 列が必要です。|  
|TemplatesNamespaceCol|VT_BSTR|InfoPath ソリューションの名前空間を格納するテンプレート フォールバック ドキュメント ライブラリの SharePoint 列の名前を指定します。|TemplatesDocLib プロパティに値が含まれている場合、このプロパティは、値を含める必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|CustomTemplatesDocLib|VT_BSTR|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を指定します。|CustomTemplatesNamespaceCol プロパティに値が含まれている場合、このプロパティは、値を含める必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|CustomTemplatesNamespaceCol|VT_BSTR|InfoPath ソリューションの名前空間を格納するテンプレート ドキュメント ライブラリの SharePoint 列の名前を指定します。|CustomTemplatesDocLib プロパティに値が含まれている場合、このプロパティは、値を含める必要があります。<br /><br /> このフィールドでは、大文字と小文字が区別されます。|なし|  
|PropertyName(n)|VT_BSTR|送信先ドキュメント ライブラリに存在する Windows SharePoint Services 列の名前を指定します。|このフィールドでは、大文字と小文字が区別されます。|16 列まで指定できます。|  
|PropertySource(n)|VT_BSTR|このメッセージに設定する列の値を指定します。|なし|最大 16 列の値を指定することができます。|  
|Timeout|VT_BSTR|Windows SharePoint Services アダプター Web サービスに対するアダプターのランタイム Web サービス呼び出しのミリ秒単位のタイムアウト値を指定します。|有効な値は、1000 ~ 2,147, 483,647 です。|既定値は 100000 です。|  
|AdapterWSPort|VT_BSTR|Windows SharePoint Services アダプター Web サービスがインストールされている IIS Web サイトの HTTP ポートを指定します。|なし|既定値は 80 です。|  
|Uri|VT_BSTR|Windows SharePoint Services 送信先フォルダーの URL への完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
> [!NOTE]
>  PropertyName2 および PropertySource2 から PropertyName16 および PropertySource16 の定義は、この文字列から省略されました。  
  
```  
<CustomProps><AdapterConfig vt="8"><SendPort xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BizTalkServer/sites/BASSite/</SiteUrl><WssLocation>Shared Documents/Purchase Orders</WssLocation><Overwrite>yes</Overwrite><NamespaceAliases>po='http://OrderProcess/POrder'</NamespaceAliases><FileName>PurchaseOrder0001.xml</FileName><OfficeIntegration>yesformlibrary</OfficeIntegration><TemplatesDocLib>Templates</TemplatesDocLib><TemplatesNamespaceCol>NamespaceFallback</TemplatesNamespaceCol><CustomTemplatesDocLib>Shared Documents</CustomTemplatesDocLib><CustomTemplatesNamespaceCol>Namespace</CustomTemplatesNamespaceCol><PropertyName1>Column1</PropertyName1><PropertySource1>Column1 Value</PropertySource1><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://biztalkserver:80/sites/BASSite/Shared%20Documents/Purchase%20Orders</uri></SendPort></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前と値のペアすべてに格納、 \<AdapterConfig\>要素。 以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。