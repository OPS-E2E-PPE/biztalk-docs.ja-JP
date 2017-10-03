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
# <a name="windows-sharepoint-services-40-support"></a><span data-ttu-id="d178a-102">Windows SharePoint Services 4.0 のサポート</span><span class="sxs-lookup"><span data-stu-id="d178a-102">Windows SharePoint Services 4.0 Support</span></span>
<span data-ttu-id="d178a-103">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 用の Windows SharePoint Services アダプターと同等の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="d178a-103">The Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] provides feature/functionality parity with the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="d178a-104">また、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは Windows SharePoint Services 4.0 で使用可能な次の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d178a-104">The Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] also supports the following functionality available with Windows SharePoint Services 4.0:</span></span>  
  
-   <span data-ttu-id="d178a-105">Windows SharePoint Services 4.0 ブログ サイトへのメッセージの送信。</span><span class="sxs-lookup"><span data-stu-id="d178a-105">Sending messages to a Windows SharePoint Services 4.0 blog site.</span></span>  
  
-   <span data-ttu-id="d178a-106">Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信。</span><span class="sxs-lookup"><span data-stu-id="d178a-106">Sending messages to and receiving message from a Windows SharePoint Services 4.0 Wiki site.</span></span>  
  
 <span data-ttu-id="d178a-107">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターは、Windows SharePoint Services 4.0 で使用可能な次の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d178a-107">The Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] does not provide support for the following features that are available in Windows SharePoint Services 4.0:</span></span>  
  
-   <span data-ttu-id="d178a-108">**ごみ箱**: の Windows SharePoint Services アダプター[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]アダプターが受信をサポートしていないか、ごみ箱に/から明示的に送信するメッセージします。</span><span class="sxs-lookup"><span data-stu-id="d178a-108">**Recycle Bin**: The Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] adapter does not support receiving, or explicitly sending messages from/to the Recycle Bin.</span></span>  
  
-   <span data-ttu-id="d178a-109">**フォルダーが一覧表示**: の Windows SharePoint Services アダプター[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]リストにメッセージを送信することができますが、一覧からメッセージを受信できません。</span><span class="sxs-lookup"><span data-stu-id="d178a-109">**Lists folders**: The Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] can send messages to lists but it cannot receive messages from lists.</span></span> <span data-ttu-id="d178a-110">Windows SharePoint Services 4.0 はリスト内のフォルダーをサポートしていますが、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d178a-110">Windows SharePoint Services 4.0 supports folders in lists but the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] does not support this feature.</span></span> <span data-ttu-id="d178a-111">したがって、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターでは、ルート フォルダー以外のリスト フォルダーにリスト項目を作成できません。</span><span class="sxs-lookup"><span data-stu-id="d178a-111">Therefore, the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] cannot create list items in a list folder other than the root folder.</span></span>  
  
-   <span data-ttu-id="d178a-112">以下のセクションでは、Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信するための [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターの使用方法、および Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d178a-112">The following sections describe in greater detail how to use the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] to send messages to a Windows SharePoint Services 4.0 blog site and how to send messages to and receive messages from a Windows SharePoint Services 4.0 Wiki site.</span></span>  
  
## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a><span data-ttu-id="d178a-113">Windows SharePoint Services 4.0 ブログ サイトへの送信</span><span class="sxs-lookup"><span data-stu-id="d178a-113">Sending to a Windows SharePoint Services 4.0 Blog Site</span></span>  
 <span data-ttu-id="d178a-114">Windows SharePoint Services 4.0 ブログ サイトでの投稿が格納されている、**ポスト**に一覧され、投稿カテゴリが定義されている、**カテゴリ** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d178a-114">In a Windows SharePoint Services 4.0 blog site, posts are stored in the **Posts** list and post categories are defined in the **Categories** list.</span></span>  
  
 <span data-ttu-id="d178a-115">Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信するアダプターで、次の値を入力してください。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d178a-115">To post a message to a Windows SharePoint Services 4.0 blog site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="d178a-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d178a-116">Property</span></span>|<span data-ttu-id="d178a-117">値</span><span class="sxs-lookup"><span data-stu-id="d178a-117">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="d178a-118">ターゲット フォルダーの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-118">Destination Folder URL</span></span>|<span data-ttu-id="d178a-119">"Lists/Posts" など、SharePoint サイトを基準とした [投稿] リストのターゲット フォルダーの URL。</span><span class="sxs-lookup"><span data-stu-id="d178a-119">Destination folder URL of the Posts list, relative to the SharePoint site, for example "Lists/Posts".</span></span>|  
|<span data-ttu-id="d178a-120">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-120">SharePoint Site URL</span></span>|<span data-ttu-id="d178a-121">たとえば http://、Windows SharePoint Services 4.0 ブログ サイトの URL*\<servername >*/ブログ/サイト/場所 *\<servername >*実際の名前のプレース ホルダーWeb サーバーです。</span><span class="sxs-lookup"><span data-stu-id="d178a-121">URL of the Windows SharePoint Services 4.0 blog site, for example http://*\<servername>*/sites/blog/ where *\<servername>* is a placeholder for the actual name of the Web server.</span></span>|  
  
 <span data-ttu-id="d178a-122">値を設定し、**カテゴリ**、**公開済み**、**タイトル**、および**本文**対応に設定して、ブログ投稿のプロパティWSS の値。メッセージの ConfigPropertiesXml コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d178a-122">Then set the values for the **Category**, **Published**, **Title**, and **Body** properties for the blog posting by setting corresponding values in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="d178a-123">これとカスタム パイプラインまたはオーケストレーションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d178a-123">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="d178a-124">たとえば、次のオーケストレーションの式では、WSS の値が設定します。ConfigPropertiesXml Message_Out メッセージのプロパティをコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="d178a-124">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message.</span></span>  
  
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
  
 <span data-ttu-id="d178a-125">この式の変数は、次のデータ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="d178a-125">The variables in this expression would use the following types:</span></span>  
  
|<span data-ttu-id="d178a-126">[変数名]</span><span class="sxs-lookup"><span data-stu-id="d178a-126">Variable name</span></span>|<span data-ttu-id="d178a-127">型</span><span class="sxs-lookup"><span data-stu-id="d178a-127">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="d178a-128">int_Category</span><span class="sxs-lookup"><span data-stu-id="d178a-128">int_Category</span></span>|<span data-ttu-id="d178a-129">System.Int32</span><span class="sxs-lookup"><span data-stu-id="d178a-129">System.Int32</span></span>|  
|<span data-ttu-id="d178a-130">str_Published</span><span class="sxs-lookup"><span data-stu-id="d178a-130">str_Published</span></span>|<span data-ttu-id="d178a-131">System.String</span><span class="sxs-lookup"><span data-stu-id="d178a-131">System.String</span></span>|  
|<span data-ttu-id="d178a-132">str_Title</span><span class="sxs-lookup"><span data-stu-id="d178a-132">str_Title</span></span>|<span data-ttu-id="d178a-133">System.String</span><span class="sxs-lookup"><span data-stu-id="d178a-133">System.String</span></span>|  
|<span data-ttu-id="d178a-134">str_Body</span><span class="sxs-lookup"><span data-stu-id="d178a-134">str_Body</span></span>|<span data-ttu-id="d178a-135">System.String</span><span class="sxs-lookup"><span data-stu-id="d178a-135">System.String</span></span>|  
  
 <span data-ttu-id="d178a-136">この方法で作成された後の状態に設定されます**未承認**サイトに表示される前にブログ所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="d178a-136">A post created this way will be set to a state of **not approved**, which will require approval by the blog owner before it is visible on the site.</span></span>  
  
 <span data-ttu-id="d178a-137">リストでサポートされている列の種類は、リストの設定ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d178a-137">The supported column types for the list can be viewed on the settings page for the list.</span></span> <span data-ttu-id="d178a-138">詳細については、Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型は、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="d178a-138">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter, see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  
  
## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="d178a-139">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリとの送受信</span><span class="sxs-lookup"><span data-stu-id="d178a-139">Sending to and Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="d178a-140">Wiki サイトを使用して、Windows SharePoint Services 4.0 サイトで、 **Wiki ページ**ドキュメント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="d178a-140">In a Windows SharePoint Services 4.0 site, a Wiki site uses the **Wiki Pages** document library.</span></span> <span data-ttu-id="d178a-141">Wiki ページ ドキュメント ライブラリ内の Wiki ページのテキストを格納する、 **Wiki Content**の UI 型を使用する列**複数行のテキスト**です。</span><span class="sxs-lookup"><span data-stu-id="d178a-141">The Wiki Pages document library stores the text of the Wiki page in a **Wiki Content** column which uses a UI type of **Multiple lines of text**.</span></span> <span data-ttu-id="d178a-142">**複数行のテキスト**UI 型に関連している、 **SPFieldType.Note** SharePoint オブジェクト モデルの種類。</span><span class="sxs-lookup"><span data-stu-id="d178a-142">The **Multiple lines of text** UI type correlates to the **SPFieldType.Note** SharePoint object model type.</span></span> <span data-ttu-id="d178a-143">Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="d178a-143">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  
  
### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="d178a-144">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリへの送信</span><span class="sxs-lookup"><span data-stu-id="d178a-144">Sending to a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="d178a-145">Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するときに**WSS です。ConfigPropertiesXml**です。</span><span class="sxs-lookup"><span data-stu-id="d178a-145">When sending messages to a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.ConfigPropertiesXml**.</span></span> <span data-ttu-id="d178a-146">Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するアダプターで、次の値を入力してください。**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する送信ポートを構成するときに ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d178a-146">To post a message to a Windows SharePoint Services 4.0 Wiki site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="d178a-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d178a-147">Property</span></span>|<span data-ttu-id="d178a-148">値</span><span class="sxs-lookup"><span data-stu-id="d178a-148">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="d178a-149">ターゲット フォルダーの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-149">Destination Folder URL</span></span>|<span data-ttu-id="d178a-150">"wikiSP" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="d178a-150">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiSP".</span></span>|  
|<span data-ttu-id="d178a-151">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-151">SharePoint Site URL</span></span>|<span data-ttu-id="d178a-152">たとえば http://、Windows SharePoint Services 4.0 Wiki サイトの URL*\<servername >*/サイト/場所 *\<servername >*実際の名前のプレース ホルダーweb サーバーです。</span><span class="sxs-lookup"><span data-stu-id="d178a-152">URL of the Windows SharePoint Services 4.0 Wiki site, for example http://*\<servername>*/sites/wiki/ where *\<servername>* is a placeholder for the actual name of the web server.</span></span>|  
  
 <span data-ttu-id="d178a-153">値を設定、 **Wiki Content** WSS に対応する値を設定して、Wiki ページのプロパティです。メッセージの ConfigPropertiesXml コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d178a-153">Then set the value for the **Wiki Content** property for the Wiki page by setting the corresponding value in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="d178a-154">これとカスタム パイプラインまたはオーケストレーションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d178a-154">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="d178a-155">たとえば、次のオーケストレーションの式によって、Message_Out メッセージの WSS.ConfigPropertiesXml コンテキスト プロパティの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d178a-155">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message:</span></span>  
  
```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 <span data-ttu-id="d178a-156">この式の str_Wiki 変数を使用して、 **System.String**データ型。</span><span class="sxs-lookup"><span data-stu-id="d178a-156">The str_Wiki variable in this expression would use the **System.String** data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d178a-157">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリはバージョン管理をサポートしていますが、BizTalk Server 2010 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d178a-157">The Windows SharePoint Services 4.0 Wiki document library supports versioning, however, the Windows SharePoint Services adapter for BizTalk Server 2010does not support versioning.</span></span> <span data-ttu-id="d178a-158">したがって、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターによって更新された Wiki ページでは、以前のバージョンは失われます。</span><span class="sxs-lookup"><span data-stu-id="d178a-158">Therefore, Wiki pages that are updated by the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] will lose their previous versions.</span></span> <span data-ttu-id="d178a-159">この制限のため、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用の Windows SharePoint Services アダプターによって受信され、別の Wiki ドキュメント ライブラリでアーカイブされた Wiki ページでは、最新のバージョンのみが保存され、他のバージョンはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="d178a-159">Because of this limitation, a Wiki page that is received by the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and archived in a different Wiki document library will preserve only its last version, with all other versions being deleted.</span></span>  
  
### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="d178a-160">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリからの受信</span><span class="sxs-lookup"><span data-stu-id="d178a-160">Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="d178a-161">Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトからメッセージを受信するときに**WSS です。InPropertiesXml**です。</span><span class="sxs-lookup"><span data-stu-id="d178a-161">When receiving messages from a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.InPropertiesXml**.</span></span>  
  
 <span data-ttu-id="d178a-162">Windows SharePoint Services 4.0 Wiki ページからメッセージを受信するには、アダプターに次の値を入力**トランスポートのプロパティ**Windows SharePoint Services アダプターを使用する受信場所を構成するときに ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d178a-162">To receive a message from a Windows SharePoint Services 4.0 Wiki page, enter the following values in the adapter **Transport Properties** dialog box when configuring a receive location that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="d178a-163">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d178a-163">Property</span></span>|<span data-ttu-id="d178a-164">値</span><span class="sxs-lookup"><span data-stu-id="d178a-164">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="d178a-165">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-165">SharePoint Site URL</span></span>|<span data-ttu-id="d178a-166">"wiki" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="d178a-166">URL of the Wiki site home page, relative to the SharePoint site, for example "wiki".</span></span>|  
|<span data-ttu-id="d178a-167">基になるドキュメント ライブラリの URL</span><span class="sxs-lookup"><span data-stu-id="d178a-167">Source Document Library URL</span></span>|<span data-ttu-id="d178a-168">"wikiRL" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="d178a-168">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiRL".</span></span>|  
  
 <span data-ttu-id="d178a-169">Wiki ページの内容を取得、 **Wiki Content**のノード、 **WSS です。InPropertiesXml**受信したメッセージのコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d178a-169">Then retrieve the wiki page contents from the **Wiki Content** node of the **WSS.InPropertiesXml** context property of the received message.</span></span> <span data-ttu-id="d178a-170">これとカスタム パイプラインまたはオーケストレーションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d178a-170">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="d178a-171">たとえば、次のオーケストレーションの式で、 **str_Wiki**変数の値が格納されます、 **Wiki Content**ノードから、 **WSS です。InPropertiesXml**のコンテキスト プロパティ、 **Message_In**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d178a-171">For example, in the following orchestration expression, the **str_Wiki** variable is populated with the value of the **Wiki Content** node from the **WSS.InPropertiesXml** context property of the **Message_In** message.</span></span> <span data-ttu-id="d178a-172">次に、 **Wiki Content**のプロパティ、 **WSS です。ConfigPropertiesXml**のコンテキスト プロパティ、 **Message_Out**メッセージがの値に設定されている、 **str_Wiki**変数。</span><span class="sxs-lookup"><span data-stu-id="d178a-172">Then, the **Wiki Content** property of the **WSS.ConfigPropertiesXml** context property of the **Message_Out** message is set to the value of the **str_Wiki** variable:</span></span>  
  
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
  
 <span data-ttu-id="d178a-173">この式の変数は、次のデータ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="d178a-173">The variables in this expression would use the following types:</span></span>  
  
|<span data-ttu-id="d178a-174">[変数名]</span><span class="sxs-lookup"><span data-stu-id="d178a-174">Variable name</span></span>|<span data-ttu-id="d178a-175">型</span><span class="sxs-lookup"><span data-stu-id="d178a-175">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="d178a-176">str_PropertiesXml</span><span class="sxs-lookup"><span data-stu-id="d178a-176">str_PropertiesXml</span></span>|<span data-ttu-id="d178a-177">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="d178a-177">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="d178a-178">doc</span><span class="sxs-lookup"><span data-stu-id="d178a-178">doc</span></span>|<span data-ttu-id="d178a-179">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="d178a-179">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="d178a-180">node</span><span class="sxs-lookup"><span data-stu-id="d178a-180">node</span></span>|<span data-ttu-id="d178a-181">System.Xml.XmlNode</span><span class="sxs-lookup"><span data-stu-id="d178a-181">System.Xml.XmlNode</span></span>|  
|<span data-ttu-id="d178a-182">str_Wiki</span><span class="sxs-lookup"><span data-stu-id="d178a-182">str_Wiki</span></span>|<span data-ttu-id="d178a-183">System.String</span><span class="sxs-lookup"><span data-stu-id="d178a-183">System.String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d178a-184">参照</span><span class="sxs-lookup"><span data-stu-id="d178a-184">See Also</span></span>  
 [<span data-ttu-id="d178a-185">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="d178a-185">Windows SharePoint Services Adapter</span></span>](../core/windows-sharepoint-services-adapter.md)