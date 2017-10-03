---
title: "Windows SharePoint Services 4.0 のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f3fedbdc4217ef5379b5e890568346a565a235
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-40-support"></a>Windows SharePoint Services 4.0 のサポート
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 用の Windows SharePoint Services アダプターと同等の機能を備えています。 また、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは Windows SharePoint Services 4.0 で使用可能な次の機能をサポートしています。  
  
-   Windows SharePoint Services 4.0 ブログ サイトへのメッセージの送信。  
  
-   Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは、Windows SharePoint Services 4.0 で使用可能な次の機能をサポートしていません。  
  
-   **ごみ箱**: の Windows SharePoint Services アダプター[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]アダプターが受信をサポートしていないか、ごみ箱に/から明示的に送信するメッセージします。  
  
-   **フォルダーが一覧表示**: の Windows SharePoint Services アダプター[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]リストにメッセージを送信することができますが、一覧からメッセージを受信できません。 Windows SharePoint Services 4.0 はリスト内のフォルダーをサポートしていますが、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。 したがって、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターでは、ルート フォルダー以外のリスト フォルダーにリスト項目を作成できません。  
  
-   以下のセクションでは、Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信するための [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターの使用方法、および Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信方法について詳しく説明します。  
  
## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>Windows SharePoint Services 4.0 ブログ サイトへの送信  
 Windows SharePoint Services 4.0 ブログ サイトでの投稿が格納されている、**ポスト**に一覧され、投稿カテゴリが定義されている、**カテゴリ** ボックスの一覧です。  
  
 Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信するアダプターで、次の値を入力してください。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|ターゲット フォルダーの URL|"Lists/Posts" など、SharePoint サイトを基準とした [投稿] リストのターゲット フォルダーの URL。|  
|SharePoint サイトの URL|たとえば http://、Windows SharePoint Services 4.0 ブログ サイトの URL*\<servername >*/ブログ/サイト/場所 *\<servername >*実際の名前のプレース ホルダーWeb サーバーです。|  
  
 値を設定し、**カテゴリ**、**公開済み**、**タイトル**、および**本文**対応に設定して、ブログ投稿のプロパティWSS の値。メッセージの ConfigPropertiesXml コンテキスト プロパティです。 これとカスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、次のオーケストレーションの式では、WSS の値が設定します。ConfigPropertiesXml Message_Out メッセージのプロパティをコンテキストです。  
  
```  
int_Category = 1;  
str_Published = Microsoft.SharePoint.Utilities.SPUtility.CreateISO8601DateTimeFromSystemDateTime(System.DateTime.Now);  
// requires a reference to Microsoft.SharePoint.dll  
str_Title = "This is the title of the post from the WSS adapter";  
str_Body = "This is the body of the post from the WSS adapter";  
  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Category</PropertyName1>  
<PropertySource1>” + int_Category + “</PropertySource1>  
<PropertyName2>Published</PropertyName2>  
<PropertySource2>” + str_Published + “</PropertySource2>  
<PropertyName3>Title</PropertyName3>  
<PropertySource3>” + str_Title + “</PropertySource3>  
<PropertyName4>Body</PropertyName4>  
<PropertySource4>” + str_Body + “</PropertySource4>  
</ConfigPropertiesXml>”;  
```  
  
 この式の変数は、次のデータ型を使用します。  
  
|[変数名]|型|  
|-------------------|----------|  
|int_Category|System.Int32|  
|str_Published|System.String|  
|str_Title|System.String|  
|str_Body|System.String|  
  
 この方法で作成された後の状態に設定されます**未承認**サイトに表示される前にブログ所有者の承認が必要です。  
  
 リストでサポートされている列の種類は、リストの設定ページに表示されます。 詳細については、Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型は、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。  
  
## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリとの送受信  
 Wiki サイトを使用して、Windows SharePoint Services 4.0 サイトで、 **Wiki ページ**ドキュメント ライブラリです。 Wiki ページ ドキュメント ライブラリ内の Wiki ページのテキストを格納する、 **Wiki Content**の UI 型を使用する列**複数行のテキスト**です。 **複数行のテキスト**UI 型に関連している、 **SPFieldType.Note** SharePoint オブジェクト モデルの種類。 Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。  
  
### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリへの送信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するときに**WSS です。ConfigPropertiesXml**です。 Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するアダプターで、次の値を入力してください。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|ターゲット フォルダーの URL|"wikiSP" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
|SharePoint サイトの URL|たとえば http://、Windows SharePoint Services 4.0 Wiki サイトの URL*\<servername >*/サイト/場所 *\<servername >*実際の名前のプレース ホルダーweb サーバーです。|  
  
 値を設定、 **Wiki Content** WSS に対応する値を設定して、Wiki ページのプロパティです。メッセージの ConfigPropertiesXml コンテキスト プロパティです。 これとカスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、次のオーケストレーションの式によって、Message_Out メッセージの WSS.ConfigPropertiesXml コンテキスト プロパティの値が設定されます。  
  
```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 この式の str_Wiki 変数を使用して、 **System.String**データ型。  
  
> [!IMPORTANT]
>  Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリはバージョン管理をサポートしていますが、BizTalk Server 2010 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。 したがって、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターによって更新された Wiki ページでは、以前のバージョンは失われます。 この制限のため、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターによって受信され、別の Wiki ドキュメント ライブラリでアーカイブされた Wiki ページでは、最新のバージョンのみが保存され、他のバージョンはすべて削除されます。  
  
### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリからの受信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトからメッセージを受信するときに**WSS です。InPropertiesXml**です。  
  
 Windows SharePoint Services 4.0 Wiki ページからメッセージを受信するには、アダプターに次の値を入力**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する受信場所を構成するときに ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|SharePoint サイトの URL|"wiki" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
|基になるドキュメント ライブラリの URL|"wikiRL" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
  
 Wiki ページの内容を取得、 **Wiki Content**のノード、 **WSS です。InPropertiesXml**受信したメッセージのコンテキスト プロパティです。 これとカスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、次のオーケストレーションの式で、 **str_Wiki**変数の値が格納されます、 **Wiki Content**ノードから、 **WSS です。InPropertiesXml**のコンテキスト プロパティ、 **Message_In**メッセージ。 次に、 **Wiki Content**のプロパティ、 **WSS です。ConfigPropertiesXml**のコンテキスト プロパティ、 **Message_Out**メッセージがの値に設定されている、 **str_Wiki**変数。  
  
```  
str_PropertiesXml = Message_In(WSS.InPropertiesXml);  
doc = doc.LoadXml(str_PropertiesXml);  
node = doc.SelectSingleNode("InPropertiesXml/Property[@name='Wiki Content']);  
str_Wiki = node.InnerText;  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 この式の変数は、次のデータ型を使用します。  
  
|[変数名]|型|  
|-------------------|----------|  
|str_PropertiesXml|System.Xml.XmlDocument|  
|doc|System.Xml.XmlDocument|  
|node|System.Xml.XmlNode|  
|str_Wiki|System.String|  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)