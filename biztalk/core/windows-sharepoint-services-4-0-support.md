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
ms.locfileid: "26009971"
---
# <a name="windows-sharepoint-services-40-support"></a><span data-ttu-id="14447-102">Windows SharePoint Services 4.0 のサポート</span><span class="sxs-lookup"><span data-stu-id="14447-102">Windows SharePoint Services 4.0 Support</span></span>
<span data-ttu-id="14447-103">BizTalk Server の Windows SharePoint Services アダプターでは、同等の機能を提供の Windows SharePoint Services アダプタで[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="14447-103">The Windows SharePoint Services adapter for BizTalk Server provides feature/functionality parity with the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="14447-104">BizTalk Server の Windows SharePoint Services アダプターには、Windows SharePoint Services 4.0 で使用可能な次の機能もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="14447-104">The Windows SharePoint Services adapter for BizTalk Server also supports the following functionality available with Windows SharePoint Services 4.0:</span></span>  
  
-   <span data-ttu-id="14447-105">Windows SharePoint Services 4.0 ブログ サイトへのメッセージの送信。</span><span class="sxs-lookup"><span data-stu-id="14447-105">Sending messages to a Windows SharePoint Services 4.0 blog site.</span></span>  
  
-   <span data-ttu-id="14447-106">Windows SharePoint Services 4.0 Wiki サイトとのメッセージの送受信。</span><span class="sxs-lookup"><span data-stu-id="14447-106">Sending messages to and receiving message from a Windows SharePoint Services 4.0 Wiki site.</span></span>  
  
 <span data-ttu-id="14447-107">BizTalk Server の Windows SharePoint Services アダプターは Windows SharePoint Services 4.0 で使用できる次の機能のサポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="14447-107">The Windows SharePoint Services adapter for BizTalk Server does not provide support for the following features that are available in Windows SharePoint Services 4.0:</span></span>  
  
-   <span data-ttu-id="14447-108">**ごみ箱**: BizTalk Server アダプター用の Windows SharePoint Services アダプターが受信をサポートしていないか、ごみ箱に/からメッセージを明示的に送信します。</span><span class="sxs-lookup"><span data-stu-id="14447-108">**Recycle Bin**: The Windows SharePoint Services adapter for BizTalk Server adapter does not support receiving, or explicitly sending messages from/to the Recycle Bin.</span></span>  
  
-   <span data-ttu-id="14447-109">**フォルダーが一覧表示**: BizTalk Server の Windows SharePoint Services アダプターは、リストにメッセージを送信できますが、一覧からメッセージを受信できません。</span><span class="sxs-lookup"><span data-stu-id="14447-109">**Lists folders**: The Windows SharePoint Services adapter for BizTalk Server can send messages to lists but it cannot receive messages from lists.</span></span> <span data-ttu-id="14447-110">Windows SharePoint Services 4.0 は、一覧にフォルダーをサポートしますが、BizTalk Server の Windows SharePoint Services アダプターはこの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="14447-110">Windows SharePoint Services 4.0 supports folders in lists but the Windows SharePoint Services adapter for BizTalk Server does not support this feature.</span></span> <span data-ttu-id="14447-111">したがって、BizTalk Server の Windows SharePoint Services アダプターでは、ルート フォルダー以外のリスト フォルダにリスト項目を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="14447-111">Therefore, the Windows SharePoint Services adapter for BizTalk Server cannot create list items in a list folder other than the root folder.</span></span>  
  
-   <span data-ttu-id="14447-112">次のセクションでは、大きいについて詳しく説明を BizTalk Server の Windows SharePoint Services アダプターを使用して、Windows SharePoint Services 4.0 ブログ サイトにメッセージを送信する方法とメッセージを送信して、Windows SharePoint Services からメッセージを受信する方法4.0 Wiki サイトです。</span><span class="sxs-lookup"><span data-stu-id="14447-112">The following sections describe in greater detail how to use the Windows SharePoint Services adapter for BizTalk Server to send messages to a Windows SharePoint Services 4.0 blog site and how to send messages to and receive messages from a Windows SharePoint Services 4.0 Wiki site.</span></span>  
  
## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a><span data-ttu-id="14447-113">Windows SharePoint Services 4.0 ブログ サイトへの送信</span><span class="sxs-lookup"><span data-stu-id="14447-113">Sending to a Windows SharePoint Services 4.0 Blog Site</span></span>  
 <span data-ttu-id="14447-114">Windows SharePoint Services 4.0 ブログ サイトでの投稿が保存されている、 **投稿** で一覧と post のカテゴリが定義されている、 **カテゴリ**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="14447-114">In a Windows SharePoint Services 4.0 blog site, posts are stored in the **Posts** list and post categories are defined in the **Categories** list.</span></span>  
  
 <span data-ttu-id="14447-115">メッセージを投稿するには、Windows SharePoint Services 4.0 ブログ サイトにするには、アダプターに次の値を入力 **トランスポートのプロパティ** Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="14447-115">To post a message to a Windows SharePoint Services 4.0 blog site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="14447-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14447-116">Property</span></span>|<span data-ttu-id="14447-117">値</span><span class="sxs-lookup"><span data-stu-id="14447-117">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="14447-118">ターゲット フォルダーの URL</span><span class="sxs-lookup"><span data-stu-id="14447-118">Destination Folder URL</span></span>|<span data-ttu-id="14447-119">"Lists/Posts" など、SharePoint サイトを基準とした [投稿] リストのターゲット フォルダーの URL。</span><span class="sxs-lookup"><span data-stu-id="14447-119">Destination folder URL of the Posts list, relative to the SharePoint site, for example "Lists/Posts".</span></span>|  
|<span data-ttu-id="14447-120">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="14447-120">SharePoint Site URL</span></span>|<span data-ttu-id="14447-121">たとえば 、Windows SharePoint Services 4.0 ブログ サイトの URL http://*\<servername\>*/sites/blog/ 場所*\<servername\>* は、Web サーバーの実際の名前のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="14447-121">URL of the Windows SharePoint Services 4.0 blog site, for example http://*\<servername\>*/sites/blog/ where *\<servername\>* is a placeholder for the actual name of the Web server.</span></span>|  
  
 <span data-ttu-id="14447-122">値を設定して、 **カテゴリ**, 、**公開**, 、**タイトル**, 、および **本文** 、WSS で対応する値を設定して、ブログ投稿のプロパティです。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。</span><span class="sxs-lookup"><span data-stu-id="14447-122">Then set the values for the **Category**, **Published**, **Title**, and **Body** properties for the blog posting by setting corresponding values in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="14447-123">これは、カスタム パイプラインまたはオーケストレーションに行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14447-123">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="14447-124">たとえば、オーケストレーションでは、次の式では、WSS の値が設定されます。ConfigPropertiesXml によって、Message_Out メッセージのプロパティをコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="14447-124">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message.</span></span>  
  
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
  
 <span data-ttu-id="14447-125">この式の変数は、次のデータ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="14447-125">The variables in this expression would use the following types:</span></span>  
  
|<span data-ttu-id="14447-126">[変数名]</span><span class="sxs-lookup"><span data-stu-id="14447-126">Variable name</span></span>|<span data-ttu-id="14447-127">型</span><span class="sxs-lookup"><span data-stu-id="14447-127">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="14447-128">int_Category</span><span class="sxs-lookup"><span data-stu-id="14447-128">int_Category</span></span>|<span data-ttu-id="14447-129">System.Int32</span><span class="sxs-lookup"><span data-stu-id="14447-129">System.Int32</span></span>|  
|<span data-ttu-id="14447-130">str_Published</span><span class="sxs-lookup"><span data-stu-id="14447-130">str_Published</span></span>|<span data-ttu-id="14447-131">System.String</span><span class="sxs-lookup"><span data-stu-id="14447-131">System.String</span></span>|  
|<span data-ttu-id="14447-132">str_Title</span><span class="sxs-lookup"><span data-stu-id="14447-132">str_Title</span></span>|<span data-ttu-id="14447-133">System.String</span><span class="sxs-lookup"><span data-stu-id="14447-133">System.String</span></span>|  
|<span data-ttu-id="14447-134">str_Body</span><span class="sxs-lookup"><span data-stu-id="14447-134">str_Body</span></span>|<span data-ttu-id="14447-135">System.String</span><span class="sxs-lookup"><span data-stu-id="14447-135">System.String</span></span>|  
  
 <span data-ttu-id="14447-136">この方法で作成された投稿は特定の状態に設定されます **承認されていない**, 、サイトに表示される前にブログ所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="14447-136">A post created this way will be set to a state of **not approved**, which will require approval by the blog owner before it is visible on the site.</span></span>  
  
 <span data-ttu-id="14447-137">リストでサポートされている列の種類は、リストの設定ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="14447-137">The supported column types for the list can be viewed on the settings page for the list.</span></span> <span data-ttu-id="14447-138">詳細については、Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型は、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="14447-138">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter, see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  
  
## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="14447-139">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリとの送受信</span><span class="sxs-lookup"><span data-stu-id="14447-139">Sending to and Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="14447-140">Wiki サイトを使用して、Windows SharePoint Services 4.0 サイトで、 **Wiki ページ** ドキュメント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="14447-140">In a Windows SharePoint Services 4.0 site, a Wiki site uses the **Wiki Pages** document library.</span></span> <span data-ttu-id="14447-141">Wiki ページのドキュメント ライブラリでの Wiki ページのテキストを格納する、 **Wiki Content** の UI 型を使用する列 **複数行のテキスト**します。</span><span class="sxs-lookup"><span data-stu-id="14447-141">The Wiki Pages document library stores the text of the Wiki page in a **Wiki Content** column which uses a UI type of **Multiple lines of text**.</span></span> <span data-ttu-id="14447-142">**複数行のテキスト** UI 型に関連している、 **SPFieldType.Note** SharePoint オブジェクト モデルの種類。</span><span class="sxs-lookup"><span data-stu-id="14447-142">The **Multiple lines of text** UI type correlates to the **SPFieldType.Note** SharePoint object model type.</span></span> <span data-ttu-id="14447-143">Windows SharePoint Services アダプターによってサポートされている Windows SharePoint Services 列の型の詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。</span><span class="sxs-lookup"><span data-stu-id="14447-143">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  
  
### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="14447-144">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリへの送信</span><span class="sxs-lookup"><span data-stu-id="14447-144">Sending to a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="14447-145">Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトにメッセージを送信するときに **WSS します。ConfigPropertiesXml**します。</span><span class="sxs-lookup"><span data-stu-id="14447-145">When sending messages to a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.ConfigPropertiesXml**.</span></span> <span data-ttu-id="14447-146">Windows SharePoint Services 4.0 Wiki サイトにメッセージを投稿するには、アダプターに、次の値を入力 **トランスポートのプロパティ** Windows SharePoint Services アダプターを使用する送信ポートを構成するときに、ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="14447-146">To post a message to a Windows SharePoint Services 4.0 Wiki site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="14447-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14447-147">Property</span></span>|<span data-ttu-id="14447-148">値</span><span class="sxs-lookup"><span data-stu-id="14447-148">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="14447-149">ターゲット フォルダーの URL</span><span class="sxs-lookup"><span data-stu-id="14447-149">Destination Folder URL</span></span>|<span data-ttu-id="14447-150">"wikiSP" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="14447-150">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiSP".</span></span>|  
|<span data-ttu-id="14447-151">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="14447-151">SharePoint Site URL</span></span>|<span data-ttu-id="14447-152">たとえば 、Windows SharePoint Services 4.0 ブログ サイトの URL http://*\<servername\>*/sites/wiki/ 場所*\<servername\>* は、Web サーバーの実際の名前のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="14447-152">URL of the Windows SharePoint Services 4.0 Wiki site, for example http://*\<servername\>*/sites/wiki/ where *\<servername\>* is a placeholder for the actual name of the web server.</span></span>|  
  
 <span data-ttu-id="14447-153">値を設定し、 **Wiki Content** 、WSS に対応する値を設定して、Wiki ページのプロパティです。メッセージのコンテキスト プロパティを ConfigPropertiesXml です。</span><span class="sxs-lookup"><span data-stu-id="14447-153">Then set the value for the **Wiki Content** property for the Wiki page by setting the corresponding value in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="14447-154">これは、カスタム パイプラインまたはオーケストレーションに行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14447-154">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="14447-155">たとえば、次のオーケストレーションの式によって、Message_Out メッセージの WSS.ConfigPropertiesXml コンテキスト プロパティの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="14447-155">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message:</span></span>  
  
```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 <span data-ttu-id="14447-156">この式の str_Wiki 変数を使用、 **System.String** データ型。</span><span class="sxs-lookup"><span data-stu-id="14447-156">The str_Wiki variable in this expression would use the **System.String** data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="14447-157">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリはバージョン管理をサポートしていますが、BizTalk Server 2010 用の Windows SharePoint Services アダプターはこの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="14447-157">The Windows SharePoint Services 4.0 Wiki document library supports versioning, however, the Windows SharePoint Services adapter for BizTalk Server 2010does not support versioning.</span></span> <span data-ttu-id="14447-158">したがって、BizTalk Server の Windows SharePoint Services アダプターによって更新された Wiki ページには、以前のバージョンは失われます。</span><span class="sxs-lookup"><span data-stu-id="14447-158">Therefore, Wiki pages that are updated by the Windows SharePoint Services adapter for BizTalk Server will lose their previous versions.</span></span> <span data-ttu-id="14447-159">この制限によりは、BizTalk Server の Windows SharePoint Services アダプターによって受信され、別の Wiki ドキュメント ライブラリでアーカイブされた Wiki ページは、最新バージョンのみ削除されている他のすべてのバージョンとを保存します。</span><span class="sxs-lookup"><span data-stu-id="14447-159">Because of this limitation, a Wiki page that is received by the Windows SharePoint Services adapter for BizTalk Server and archived in a different Wiki document library will preserve only its last version, with all other versions being deleted.</span></span>  
  
### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="14447-160">Windows SharePoint Services 4.0 Wiki ドキュメント ライブラリからの受信</span><span class="sxs-lookup"><span data-stu-id="14447-160">Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="14447-161">Wiki ページの内容がという名前の Windows SharePoint Services アダプター コンテキスト プロパティ内に格納されている Windows SharePoint Services 4.0 Wiki サイトからのメッセージを受信するときに **WSS します。InPropertiesXml**します。</span><span class="sxs-lookup"><span data-stu-id="14447-161">When receiving messages from a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.InPropertiesXml**.</span></span>  
  
 <span data-ttu-id="14447-162">Windows SharePoint Services 4.0 Wiki ページからのメッセージを受信するには、アダプターに、次の値を入力 **トランスポートのプロパティ** と Windows SharePoint Services アダプターを使用する受信場所の構成 ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="14447-162">To receive a message from a Windows SharePoint Services 4.0 Wiki page, enter the following values in the adapter **Transport Properties** dialog box when configuring a receive location that uses the Windows SharePoint Services adapter:</span></span>  
  
|<span data-ttu-id="14447-163">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14447-163">Property</span></span>|<span data-ttu-id="14447-164">値</span><span class="sxs-lookup"><span data-stu-id="14447-164">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="14447-165">SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="14447-165">SharePoint Site URL</span></span>|<span data-ttu-id="14447-166">"wiki" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="14447-166">URL of the Wiki site home page, relative to the SharePoint site, for example "wiki".</span></span>|  
|<span data-ttu-id="14447-167">基になるドキュメント ライブラリの URL</span><span class="sxs-lookup"><span data-stu-id="14447-167">Source Document Library URL</span></span>|<span data-ttu-id="14447-168">"wikiRL" など、SharePoint サイトを基準とした Wiki サイトのホーム ページの URL。</span><span class="sxs-lookup"><span data-stu-id="14447-168">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiRL".</span></span>|  
  
 <span data-ttu-id="14447-169">Wiki ページのコンテンツを取得、 **Wiki Content** のノード、 **WSS します。InPropertiesXml** 受信したメッセージのコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="14447-169">Then retrieve the wiki page contents from the **Wiki Content** node of the **WSS.InPropertiesXml** context property of the received message.</span></span> <span data-ttu-id="14447-170">これは、カスタム パイプラインまたはオーケストレーションに行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14447-170">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="14447-171">たとえば、次のオーケストレーションの式で、 **str_Wiki** の値を持つ変数が設定されます、 **Wiki Content** ノードから、 **WSS します。InPropertiesXml** のコンテキスト プロパティ、 **Message_In** メッセージです。</span><span class="sxs-lookup"><span data-stu-id="14447-171">For example, in the following orchestration expression, the **str_Wiki** variable is populated with the value of the **Wiki Content** node from the **WSS.InPropertiesXml** context property of the **Message_In** message.</span></span> <span data-ttu-id="14447-172">次に、 **Wiki Content** のプロパティ、 **WSS します。ConfigPropertiesXml** のコンテキスト プロパティ、 **Message_Out** メッセージは、の値に設定されて、 **str_Wiki** 変数。</span><span class="sxs-lookup"><span data-stu-id="14447-172">Then, the **Wiki Content** property of the **WSS.ConfigPropertiesXml** context property of the **Message_Out** message is set to the value of the **str_Wiki** variable:</span></span>  
  
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
  
 <span data-ttu-id="14447-173">この式の変数は、次のデータ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="14447-173">The variables in this expression would use the following types:</span></span>  
  
|<span data-ttu-id="14447-174">[変数名]</span><span class="sxs-lookup"><span data-stu-id="14447-174">Variable name</span></span>|<span data-ttu-id="14447-175">型</span><span class="sxs-lookup"><span data-stu-id="14447-175">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="14447-176">str_PropertiesXml</span><span class="sxs-lookup"><span data-stu-id="14447-176">str_PropertiesXml</span></span>|<span data-ttu-id="14447-177">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="14447-177">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="14447-178">doc</span><span class="sxs-lookup"><span data-stu-id="14447-178">doc</span></span>|<span data-ttu-id="14447-179">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="14447-179">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="14447-180">node</span><span class="sxs-lookup"><span data-stu-id="14447-180">node</span></span>|<span data-ttu-id="14447-181">System.Xml.XmlNode</span><span class="sxs-lookup"><span data-stu-id="14447-181">System.Xml.XmlNode</span></span>|  
|<span data-ttu-id="14447-182">str_Wiki</span><span class="sxs-lookup"><span data-stu-id="14447-182">str_Wiki</span></span>|<span data-ttu-id="14447-183">System.String</span><span class="sxs-lookup"><span data-stu-id="14447-183">System.String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14447-184">参照</span><span class="sxs-lookup"><span data-stu-id="14447-184">See Also</span></span>  
 [<span data-ttu-id="14447-185">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="14447-185">Windows SharePoint Services Adapter</span></span>](../core/windows-sharepoint-services-adapter.md)