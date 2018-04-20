---
title: Windows SharePoint Services 4.0 のサポート |Microsoft ドキュメント
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
ms.openlocfilehash: ff27ebd5804f3603aabf3bae24e469c2028234f2
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="windows-sharepoint-services-40-support"></a>Windows SharePoint Services 4.0 のサポート
BizTalk Server の Windows SharePoint Services アダプターでは、同等の機能を提供の Windows SharePoint Services アダプタで[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]です。 BizTalk Server の Windows SharePoint Services アダプターには、Windows SharePoint Services 4.0 で使用可能な次の機能もサポートしています。  
  
-   Windows SharePoint Services 4.0 ブログ サイトへのメッセージの送信。  
  
-   Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信。  
  
 BizTalk Server の Windows SharePoint Services アダプターは Windows SharePoint Services 4.0 で使用できる次の機能のサポートを提供していません。  
  
-   **ごみ箱**: BizTalk Server アダプター用の Windows SharePoint Services アダプターが受信をサポートしていないか、ごみ箱に/からメッセージを明示的に送信します。  
  
-   **フォルダーが一覧表示**: BizTalk Server の Windows SharePoint Services アダプターは、リストにメッセージを送信できますが、一覧からメッセージを受信できません。 Windows SharePoint Services 4.0 は、一覧にフォルダーをサポートしますが、BizTalk Server の Windows SharePoint Services アダプターはこの機能をサポートしていません。 したがって、BizTalk Server の Windows SharePoint Services アダプターでは、ルート フォルダー以外のリスト フォルダにリスト項目を作成することはできません。  
  
-   次のセクションでは、大きいについて詳しく説明を BizTalk Server の Windows SharePoint Services アダプターを使用して、Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信する方法とメッセージを送信して、Windows SharePoint Services からメッセージを受信する方法4.0 Wiki サイトです。  
  
## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>Windows SharePoint Services 4.0 ブログ サイトへの送信  
 Windows SharePoint Services 4.0 ブログ サイトでの投稿が保存されている、 **投稿** で一覧と post のカテゴリが定義されている、 **カテゴリ**  ボックスの一覧です。  
  
 メッセージを投稿するには、Windows SharePoint Services 4.0 ブログ サイトにするには、アダプターに次の値を入力 **トランスポートのプロパティ** Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|ターゲット フォルダーの URL|"Lists/Posts" など、SharePoint サイトを基準とした [投稿] リストのターゲット フォルダーの URL。|  
|SharePoint サイトの URL|たとえば http://、Windows SharePoint Services 4.0 ブログ サイトの URL*\<servername\>*/ブログ/サイト/場所*\<servername\>*は、Web サーバーの実際の名前のプレース ホルダーです。|  
  
 値を設定して、 **カテゴリ**, 、**公開**, 、**タイトル**, 、および **本文** 、WSS で対応する値を設定して、ブログ投稿のプロパティです。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。 これは、カスタム パイプラインまたはオーケストレーションに行うことができます。 たとえば、オーケストレーションでは、次の式では、WSS の値が設定されます。ConfigPropertiesXml によって、Message_Out メッセージのプロパティをコンテキストです。  
  
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
  
 この方法で作成された投稿は特定の状態に設定されます **承認されていない**, 、サイトに表示される前にブログ所有者の承認が必要です。  
  
 リストでサポートされている列の種類は、リストの設定ページに表示されます。 詳細については、Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型は、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。  
  
## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリとの送受信  
 Wiki サイトを使用して、Windows SharePoint Services 4.0 サイトで、 **Wiki ページ** ドキュメント ライブラリです。 Wiki ページのドキュメント ライブラリでの Wiki ページのテキストを格納する、 **Wiki Content** の UI 型を使用する列 **複数行のテキスト**します。 **複数行のテキスト** UI 型に関連している、 **SPFieldType.Note** SharePoint オブジェクト モデルの種類。 Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。  
  
### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリへの送信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するときに **WSS します。ConfigPropertiesXml**します。 Windows SharePoint Services 4.0 Wiki サイトにメッセージを投稿するには、アダプターに、次の値を入力 **トランスポートのプロパティ** Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|ターゲット フォルダーの URL|"wikiSP" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
|SharePoint サイトの URL|たとえば http://、Windows SharePoint Services 4.0 Wiki サイトの URL*\<servername\>*/サイト/場所*\<servername\>*は、web サーバーの実際の名前のプレース ホルダーです。|  
  
 値を設定し、 **Wiki Content** 、WSS に対応する値を設定して、Wiki ページのプロパティです。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。 これは、カスタム パイプラインまたはオーケストレーションに行うことができます。 たとえば、次のオーケストレーションの式によって、Message_Out メッセージの WSS.ConfigPropertiesXml コンテキスト プロパティの値が設定されます。  
  
```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 この式の str_Wiki 変数を使用、 **System.String** データ型。  
  
> [!IMPORTANT]
>  Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリはバージョン管理をサポートしていますが、BizTalk Server 2010 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。 したがって、BizTalk Server の Windows SharePoint Services アダプターによって更新された Wiki ページには、以前のバージョンは失われます。 この制限によりは、BizTalk Server の Windows SharePoint Services アダプターによって受信され、別の Wiki ドキュメント ライブラリでアーカイブされた Wiki ページは、最新バージョンのみ削除されている他のすべてのバージョンとを保存します。  
  
### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリからの受信  
 Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトからのメッセージを受信するときに **WSS します。InPropertiesXml**します。  
  
 Windows SharePoint Services 4.0 Wiki ページからのメッセージを受信するには、アダプターに、次の値を入力 **トランスポートのプロパティ** と Windows SharePoint Services アダプターを使用する受信場所の構成 ダイアログ ボックス。  
  
|プロパティ|値|  
|--------------|-----------|  
|SharePoint サイトの URL|"wiki" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
|基になるドキュメント ライブラリの URL|"wikiRL" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。|  
  
 Wiki ページのコンテンツを取得、 **Wiki Content** のノード、 **WSS します。InPropertiesXml** 受信したメッセージのコンテキスト プロパティです。 これは、カスタム パイプラインまたはオーケストレーションに行うことができます。 たとえば、次のオーケストレーションの式で、 **str_Wiki** の値を持つ変数が設定されます、 **Wiki Content** ノードから、 **WSS します。InPropertiesXml** のコンテキスト プロパティ、 **Message_In** メッセージです。 次に、 **Wiki Content** のプロパティ、 **WSS します。ConfigPropertiesXml** のコンテキスト プロパティ、 **Message_Out** メッセージは、の値に設定されて、 **str_Wiki** 変数。  
  
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