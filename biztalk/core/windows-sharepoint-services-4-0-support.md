---
title: Windows SharePoint Services 4.0 のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6920de947165f7f3065f190d077d55dcbef30c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971035"
---
# <a name="windows-sharepoint-services-40-support"></a>Windows SharePoint Services 4.0 のサポート
BizTalk Server の Windows SharePoint Services アダプターは、Windows SharePoint Services アダプタで同等の機能を提供します[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]します。 BizTalk Server の Windows SharePoint Services アダプターでは、Windows SharePoint Services 4.0 で使用できる次の機能もサポートしています。  

- Windows SharePoint Services 4.0 ブログ サイトへのメッセージの送信。  

- Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信。  

  BizTalk Server の Windows SharePoint Services アダプターでは、Windows SharePoint Services 4.0 で使用できる次の機能のサポートは提供されません。  

- **ごみ箱**: BizTalk Server アダプター用の Windows SharePoint Services アダプターが受信をサポートしていないか、ごみ箱との間にメッセージを明示的に送信します。  

- **フォルダーを一覧表示**: BizTalk Server 用の Windows SharePoint Services アダプターはリストにメッセージを送信することができますが、リストからメッセージを受信できません。 Windows SharePoint Services 4.0 は、リスト内のフォルダーをサポートしていますが、BizTalk Server の Windows SharePoint Services アダプタがこの機能をサポートしていません。 そのため、BizTalk Server の Windows SharePoint Services アダプターでは、ルート フォルダー以外のフォルダーの一覧でリスト項目を作成することはできません。  

- BizTalk Server の Windows SharePoint Services アダプターを使用して、Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信する方法とメッセージを送信し、Windows SharePoint Services からメッセージを受信する方法、さらに詳しく、次のセクションについて説明します4.0 Wiki サイトです。  

## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>Windows SharePoint Services 4.0 ブログ サイトへの送信  
 Windows SharePoint Services 4.0 ブログ サイトでの投稿が格納されている、**投稿**に一覧され、投稿カテゴリが定義されている、**カテゴリ**一覧。  

 Windows SharePoint Services 4.0 ブログ サイトへのメッセージを投稿、アダプターで、次の値を入力します。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。  


|        プロパティ        |                                                                                            値                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ターゲット フォルダーの URL |                                            "Lists/Posts" など、SharePoint サイトを基準とした [投稿] リストのターゲット フォルダーの URL。                                            |
|  SharePoint サイトの URL   | たとえば 、Windows SharePoint Services 4.0 ブログ サイトの URL http://<em>\<servername\></em>/sites/blog/ 場所*\<servername\>* は、Web サーバーの実際の名前のプレース ホルダーです。 |

 値を設定して、**カテゴリ**、 **Published**、**タイトル**、および**本文**対応に設定して、ブログ投稿のプロパティWSS の値。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。 これは、カスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、オーケストレーションでは、次の式は、WSS で値を設定するは。ConfigPropertiesXml Message_Out メッセージのプロパティをコンテキストです。  

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

 この方法で作成された後の状態に設定されます**承認されていない**サイトに表示される前に、ブログ所有者の承認が必要です。  

 リストでサポートされている列の種類は、リストの設定ページに表示されます。 Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の種類の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)します。  

## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリとの送受信  
 Wiki サイトを使用して、Windows SharePoint Services 4.0 サイトで、 **Wiki ページ**ドキュメント ライブラリです。 Wiki ページのドキュメント ライブラリ、Wiki ページのテキストを格納する、 **Wiki Content**の UI 型を使用する列**複数行のテキスト**します。 **複数行のテキスト**UI 型、 **SPFieldType.Note** SharePoint オブジェクト モデルの種類。 Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)します。  

### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリへの送信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するときに**WSS。ConfigPropertiesXml**します。 Windows SharePoint Services 4.0 Wiki サイトにメッセージを投稿、アダプターで、次の値を入力します。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。  


|        プロパティ        |                                                                                            値                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ターゲット フォルダーの URL |                                                   "wikiSP" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。                                                    |
|  SharePoint サイトの URL   | たとえば 、Windows SharePoint Services 4.0 ブログ サイトの URL http://<em>\<servername\></em>/sites/wiki/ 場所*\<servername\>* は、Web サーバーの実際の名前のプレース ホルダーです。 |

 値を設定し、 **Wiki Content** WSS で対応する値を設定して、Wiki ページのプロパティ。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。 これは、カスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、次のオーケストレーションの式によって、Message_Out メッセージの WSS.ConfigPropertiesXml コンテキスト プロパティの値が設定されます。  

```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 この式の str_Wiki 変数が使用して、 **System.String**データ型。  

> [!IMPORTANT]
>  Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリはバージョン管理をサポートしていますが、BizTalk Server 2010 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。 そのため、BizTalk server、Windows SharePoint Services アダプタによって更新された Wiki ページには、以前のバージョンが失われます。 この制限により、Wiki ページが BizTalk Server の Windows SharePoint Services アダプターによって受信され、別の Wiki ドキュメント ライブラリにアーカイブで、最後のバージョンのみ、他のすべてのバージョンは削除されますが保持されます。  

### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリからの受信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトからメッセージを受信するときに**WSS。InPropertiesXml**します。  

 を Windows SharePoint Services 4.0 Wiki ページからメッセージを受信するには、アダプターに次の値を入力**トランスポートのプロパティ**、Windows SharePoint Services アダプターを使用する受信場所を構成するときに、ダイアログ ボックス。  

|プロパティ|値|  
|--------------|-----------|  
|SharePoint サイトの URL|"wiki" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
|基になるドキュメント ライブラリの URL|"wikiRL" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  

 Wiki ページの内容を取得し、 **Wiki Content**のノード、 **WSS。InPropertiesXml**受信したメッセージのコンテキスト プロパティ。 これは、カスタム パイプラインまたはオーケストレーションで実行できます。 たとえば、次のオーケストレーションの式で、 **str_Wiki**変数には、値が設定されて、 **Wiki Content**ノードから、 **WSS。InPropertiesXml**のコンテキスト プロパティ、 **Message_In**メッセージ。 次に、 **Wiki Content**のプロパティ、 **WSS。ConfigPropertiesXml**のコンテキスト プロパティ、 **Message_Out**メッセージがの値に設定されている、 **str_Wiki**変数。  

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