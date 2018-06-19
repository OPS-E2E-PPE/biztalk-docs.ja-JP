---
title: Windows SharePoint Services アダプターのプロパティのリファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfigCustomTemplatesDocLib property [Windows SharePoint Services adapters]
- InFileSize property [Windows SharePoint Services adapters]
- InIconUrl property [Windows SharePoint Services adapters]
- InOfficeIntegration property [Windows SharePoint Services adapters]
- code samples, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, properties
- ConfigCustomTemplatesNamespaceCol property [Windows SharePoint Services adapters]
- configuring [Windows SharePoint Services adapters], properties
- ConfigTemplatesDocLib property [Windows SharePoint Services adapters]
- InPropertiesXml property [Windows SharePoint Services adapters]
- InItemId property [Windows SharePoint Services adapters]
- InListName property [Windows SharePoint Services adapters]
- InArchivedMsgUrl property [Windows SharePoint Services adapters]
- Filename property [Windows SharePoint Services adapters]
- InListUrl property [Windows SharePoint Services adapters]
- ConfigTemplatesNamespaceCol property [Windows SharePoint Services adapters]
- InLastModifiedBy property [Windows SharePoint Services adapters]
- ConfigOverwrite property [Windows SharePoint Services adapters]
- ConfigPropertiesXml property [Windows SharePoint Services adapters]
- TransmittedFileLocation property [Windows SharePoint Services adapters]
- InTitle property [Windows SharePoint Services adapters]
- Windows SharePoint Services adapters, code samples
- InCreated property [Windows SharePoint Services adapters]
- InCreatedBy property [Windows SharePoint Services adapters]
- InLastModified property [Windows SharePoint Services adapters]
- URL property [Windows SharePoint Services adapters]
- InEditUrl property [Windows SharePoint Services adapters]
- ConfigOfficeIntegration property [Windows SharePoint Services adapters]
- ConfigTimeout property [Windows SharePoint Services adapters]
- ConfigNamespaceAliases property [Windows SharePoint Services adapters]
- ConfigAdapterWSPort property [Windows SharePoint Services adapters]
ms.assetid: c64c43ac-05bb-427c-987a-71663ae8e43d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691708378d778eb0c91be73fe2b775d5bfd27cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22291754"
---
# <a name="windows-sharepoint-services-adapter-properties-reference"></a>Windows SharePoint Services アダプタのプロパティに関するリファレンス
次の Windows SharePoint Services アダプタのプロパティは、BizTalk Server に昇格されるか、送信メッセージの送信ポート構成オプションを指定するために使用されます。 これらのプロパティを使用すると、メッセージに関する Windows SharePoint Services の情報にアクセスしたり、オーケストレーション内部から Windows SharePoint Services アダプタに情報を提供することができます。  
  
## <a name="message-property-precedence"></a>メッセージ プロパティの優先順位  
 オーケストレーションおよび送信ポートで定義されたメッセージ プロパティを優先する際、優先順位の規則があります。  
  
 優先順位の規則は次のとおりです。  
  
1.  PropertiesXML 内部のオーケストレーションで定義されたプロパティ  
  
2.  オーケストレーションで定義されたプロパティ  
  
3.  Property Name または Property Source コレクションの内部に送信ポート レベルで定義されたプロパティ  
  
4.  送信ポート レベルで定義されたプロパティ  
  
## <a name="considerations-and-known-issues"></a>考慮事項と既知の問題  
 Windows SharePoint Services アダプタのプロパティに関する考慮事項は次のとおりです。  
  
-   オーケストレーション内のプロパティの一覧は、プロパティの位置に基づいてポートで定義されているプロパティとマージされます。 競合が発生した場合、オーケストレーション プロパティが送信ポート プロパティよりも優先されます。  
  
## <a name="property-types"></a>プロパティの種類  
  
|プロパティの型|Description|  
|-------------------|-----------------|  
|**IN**|IN プロパティは、Windows SharePoint Services から値を取得する BizTalk Server のプロパティです。 **注:** オーケストレーション内からこれらのプロパティを変更しないでください。|  
|**構成**|CONFIG プロパティは、BizTalk オーケストレーションまたはカスタム パイプラインから値を取得するプロパティです。 この値は、送信メッセージの送信先を判断する際に Windows SharePoint Services アダプタで使用されます。 CONFIG プロパティを使用すると、オーケストレーションやカスタム パイプライン内の一部のプロパティの値を指定できます。このプロパティを使用しない場合は、送信ポートで定義する必要があります。 URL プロパティを除き、IN または CONFIG で始まらないプロパティは、IN および CONFIG の両方になります。|  
|**昇格**|PROMOTED プロパティは、コンテンツ ベースのルーティング (CBR) で使用できます。 PROMOTED に設定されていないプロパティは、CBR で使用できません。 **注:** cbr、昇格されたプロパティのみを使用できますが、すべてのアダプター プロパティが CBR フィルタ エディタで表示、します。|  
|**特殊です**|なし|  
  
> [!NOTE]
>  すべてのプロパティは、http://schemas.microsoft.com/BizTalk/2006/WindowsSharePointServices-properties 名前空間に存在し、`WSS.<WSS_Property_Name>` 構文を使用してオーケストレーションまたは送信ポート フィルターからアクセスできます。  
  
## <a name="property-list"></a>プロパティの一覧  
  
|Windows SharePoint Services の標準の列|Windows SharePoint Services のプロパティ名|型|Description|プロパティの型|  
|-------------------------------------------------|--------------------------------------------------------|----------|-----------------|-------------------|  
|名前|Filename|xs:string|Windows SharePoint Services ファイルの拡張子の付いたファイル名。 ファイル名 (拡張子を含む) は、ドキュメント ライブラリ内で一意です。|IN/CONFIG/PROMOTED|  
|なし|URL|xs:string|ファイルの URL。|IN/PROMOTED|  
|なし|TransmittedFileLocation|なし|このプロパティは、統合の目的でビジネス アクティビティ監視 (BAM) で使用されます。オーケストレーションでは使用できません。|SPECIAL|  
|なし|InArchivedMsgUrl|xs:string|アーカイブ ドキュメント ライブラリ内のファイルの URL。 このプロパティは、受信場所でメッセージをアーカイブしていない場合、使用できません。|IN/PROMOTED|  
|型|InIconUrl|xs:string|ドキュメントを表す際に使用される Windows SharePoint Services アイコンの URL。|IN|  
|Title|InTitle|xs:string|Windows SharePoint Service ファイルのタイトル。 ファイル名とは異なります。 タイトルについては、必ずしもドキュメント ライブラリ内で一意にする必要はありません。|IN/PROMOTED|  
|[更新日時]|InLastModified|xs:dateTime|Windows SharePoint Service の最終更新日時。|IN/PROMOTED|  
|[変更者]|InLastModifiedBy|xs:string|ファイルを最後に変更したユーザーの名前。|IN/PROMOTED|  
|ID|InItemId|xs:int|ファイルの ID。 ファイルへのアクセスに使用できる、ドキュメント ライブラリ内で一意な整数です。|IN|  
|[編集]|InEditUrl|xs:string|ファイルのプロパティを編集する際にアクセスできる URL。|IN|  
|Created|InCreated|xs:dateTime|Windows SharePoint Service ファイルが作成された日時。|IN/PROMOTED|  
|[作成者]|InCreatedBy|xs:string|ファイルを作成したユーザー。|IN/PROMOTED|  
|ファイル サイズ|InFileSize|xs:int|Windows SharePoint Services ファイルのサイズ。|IN|  
|なし|InListName|xs:string|このファイルが存在するドキュメント ライブラリの名前。|IN/PROMOTED|  
|なし|InListUrl|xs:string|ドキュメント ライブラリの URL、つまり、このファイルが存在するドキュメント ライブラリ フォルダ。|IN|  
|なし|InPropertiesXml|xs:string|標準およびユーザー定義の Windows SharePoint Services 列をすべて含むフラット XML ドキュメント。 このドキュメントにより、オーケストレーションから任意の Windows SharePoint Services 列の値 (ユーザー定義列の値など) にアクセスできます。 **注:** 16 列の制限はありません。 **注:** このトピックの次のセクションにある InPropertiesXml 値のサンプルを参照してください。|IN|  
|なし|InOfficeIntegration|xs:string|受信場所の値に基づきます。 `yes`、`no`、または `optional` のいずれかになります。|IN|  
|なし|ConfigOverwrite|xs:string|"Yes" を指定すると、同じ名前を持つ既存のファイルが上書きされます。 "No" を指定すると、同じ名前のファイルが存在する場合にエラーが生成されます。 "Rename" を指定すると、一意なシーケンスをファイル名に追加することにより、ファイルが一意な名前に変更されます。 **注:** 物理送信ポートの「上書き」フィールドに似ています。 **注:** 'Orchestration' は、このフィールドの有効な値ではありません。|CONFIG|  
|なし|ConfigNamespaceAliases|xs:string|XPATH のエイリアス定義。|CONFIG|  
|なし|ConfigOfficeIntegration|xs:string|OfficeImporters を呼び出す必要がある場合は 'Yes' を指定します。 メッセージをそのまま処理する場合は 'No' を指定します。 'Optional' を指定すると、IP ソリューションが見つかる場合は 'Yes'、それ以外の場合は 'No' になります。 **注:** 物理送信ポートの"Microsoft Office Integration"フィールドに似ています。 **注:** 'Orchestration' は、このフィールドの有効な値ではありません。|CONFIG|  
|なし|ConfigTemplatesDocLib|xs:string|フォールバック ドキュメント ライブラリの名前。 2 番目に検索される場所です。 **注:** 物理送信ポートの [テンプレート フォールバック ドキュメント ライブラリ] フィールドに似ています。|CONFIG|  
|なし|ConfigTemplatesNamespaceCol|xs:string|フォールバック ドキュメント ライブラリの名前空間列名。 **注:** 物理送信ポートの 'テンプレート フォールバック Namespace 列' フィールドに似ています。|CONFIG|  
|なし|ConfigCustomTemplatesDocLib|xs:string|プライマリ ドキュメント ライブラリの名前。 最初に検索される場所です。 **注:** 物理送信ポートの [テンプレート ドキュメント ライブラリ] フィールドに似ています。|CONFIG|  
|なし|ConfigCustomTemplatesNamespaceCol|xs:string|プライマリ ドキュメント ライブラリの名前空間列名。 **注:** 物理送信ポートの [テンプレート Namespace 列] フィールドに似ています。|CONFIG|  
|なし|ConfigPropertiesXml|xs:string|後から Windows SharePoint Services で更新される Windows SharePoint Services 列の名前と値をすべて含むフラット XML ドキュメント。 このドキュメントにより、オーケストレーションの開発者は、SharePoint で後続のメッセージが作成されるように SharePoint 列の値を設定できます。 **注:** と列 n の値フィールドの物理送信ポートが列 n で利用できる機能に似ています。 **注:** 16 列の制限があります。 **注:** このトピックの「ConfigPropertiesXml 値サンプルを参照してください。|CONFIG|  
|なし|ConfigTimeout|xs:int|Web サービス呼び出しのタイムアウト (ミリ秒単位)。|CONFIG|  
|なし|ConfigAdapterWSPort|xs:int|アダプタがインストールおよび構成されているポートまたは IIS Web サイト。 **注:** オーケストレーションでの無効なポートの構成値物理送信ポートの値は、定義されているオーケストレーションの値をオーバーライドする場合でも、メッセージが中断されます。|CONFIG|  
  
## <a name="sample-inpropertiesxml"></a>InPropertiesXml のサンプル  
 InPropertiesXml のサンプル XML を次に示します。  
  
```  
<InPropertiesXml>  
     <Property name="InItemId">2</Property>  
     <Property name="Created">12/14/2004 1:30:31 PM</Property>  
     <Property name="Author">3;#John Doe</Property>  
     <Property name="Modified">12/14/2004 1:30:31 PM</Property>  
     <Property name="Editor">3;#John Doe</Property>  
     <Property name="_ModerationStatus">0</Property>  
     <Property name="_ModerationComments" />  
     <Property name="FileRef">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="FileDirRef">2;#sites/BASSite/SourceLibrary</Property>  
     <Property name="InLastModified">2004-12-14 13:30:31</Property>  
     <Property name="InCreated">2004-12-14 13:30:31</Property>  
     <Property name="InFileSize">7338</Property>  
     <Property name="FSObjType">0</Property>  
     <Property name="CheckedOutUserId">2;#3</Property>  
     <Property name="Filename">PO1.xml</Property>  
     <Property name="VirusStatus">2;#7338</Property>  
     <Property name="CheckedOutTitle">2;#John Doe</Property>  
     <Property name="LinkCheckedOutTitle">John Doe</Property>  
     <Property name="InLastModifiedBy">MyDomain\jdoe</Property>  
     <Property name="InCreatedBy">MyDomain\jdoe</Property>  
     <Property name="owshiddenversion">1</Property>  
     <Property name="File_x0020_Type">xml</Property>  
     <Property name="HTML_x0020_File_x0020_Type" />  
     <Property name="_SourceUrl" />  
     <Property name="_SharedFileIndex" />  
     <Property name="LinkFilenameNoMenu">PO1.xml</Property>  
     <Property name="LinkFilename">PO1.xml</Property>  
     <Property name="SelectTitle">2</Property>  
     <Property name="SelectFilename">2</Property>  
     <Property name="Edit">xml</Property>  
     <Property name="InIconUrl">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="Url">http://localhost:80/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="EncodedAbsUrl">PO1</Property>  
     <Property name="BaseName">7338</Property>  
     <Property name="FileSizeDisplay" />  
     <Property name="InstanceID">200</Property>  
     <Property name="Order" />  
     <Property name="InTitle" />  
     <Property name="ColumnOne" />  
     <Property name="ColumnTwo" />  
     <Property name="ColumnThree" />  
     <Property name="ColumnFour" />  
     <Property name="InListName">SourceLibrary</Property>  
     <Property name="InListUrl">http://localhost:80/sites/BASSite/SourceLibrary</Property>  
     <Property name="InEditUrl">http://localhost:80/sites/BASSite/SourceLibrary/Forms/EditForm.aspx?ID=2</Property>  
     <Property name="InOfficeIntegration">yes</Property>  
</InPropertiesXml>  
```  
  
## <a name="sample-configpropertiesxml"></a>ConfigPropertiesXml のサンプル  
 ConfigPropertiesXml のサンプル XML を次に示します。  
  
```  
<ConfigPropertiesXml>  
     <PropertyName1>PO number</PropertyName1>  
     <PropertySource1>%XPATH=//orchns:PurchaseOrder/orchns:Header/orchns:ID%</PropertySource1>  
     <PropertyName2>Charge To</PropertyName2>  
     <PropertySource2>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:chargeTo%</PropertySource2>  
     <PropertyName3>PO Priority</PropertyName3>  
     <PropertySource3>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:priority%</PropertySource3>  
     <PropertyName4>Order Date</PropertyName4>  
     <PropertySource4>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:dateOrdered%</PropertySource4>  
</ConfigPropertiesXml>  
```  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Windows SharePoint Services 列の型のサポート](../core/supported-windows-sharepoint-services-column-types.md)