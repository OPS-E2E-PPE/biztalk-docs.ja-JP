---
title: "TIBCO Enterprise Message Service トランスポート プロパティの設定、受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, setting transport properties
- transport properties, setting for receive port
- setting transport properties, receive port
ms.assetid: bccddf84-d92e-469f-aa6f-4234c91a0be9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94229364e3bed8faaf1407603f17db76c70e6bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a><span data-ttu-id="517b7-102">TIBCO Enterprise Message Service 受信ポートのトランスポート プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="517b7-102">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>
<span data-ttu-id="517b7-103">TIBCO Enterprise Message System (EMS) の受信場所を**URL**と**Target Namespace** TIBCO EMS システムには、必要な唯一の構成値。</span><span class="sxs-lookup"><span data-stu-id="517b7-103">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>  
  
### <a name="to-specify-tibco-ems-transport-properties"></a><span data-ttu-id="517b7-104">TIBCO EMS トランスポートのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="517b7-104">To specify TIBCO EMS transport properties</span></span>  
  
1.  <span data-ttu-id="517b7-105">展開して、**システム定義**し、TIBCO EMS サーバーに接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="517b7-105">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="517b7-106">展開**メッセージの処理**し必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="517b7-106">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="517b7-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="517b7-107">Parameter</span></span>|<span data-ttu-id="517b7-108">Description</span><span class="sxs-lookup"><span data-stu-id="517b7-108">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="517b7-109">**メッセージ セレクター**</span><span class="sxs-lookup"><span data-stu-id="517b7-109">**Message Selector**</span></span>|<span data-ttu-id="517b7-110">メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。</span><span class="sxs-lookup"><span data-stu-id="517b7-110">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="517b7-111">受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。</span><span class="sxs-lookup"><span data-stu-id="517b7-111">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="517b7-112">メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="517b7-112">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="517b7-113">構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="517b7-113">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="517b7-114">たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="517b7-114">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="517b7-115">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="517b7-115">**Retry Count**</span></span>|<span data-ttu-id="517b7-116">トランスポートの再試行の回数です。</span><span class="sxs-lookup"><span data-stu-id="517b7-116">The retry count for the transport.</span></span> <span data-ttu-id="517b7-117">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="517b7-117">Default value is 0.</span></span>|  
    |<span data-ttu-id="517b7-118">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="517b7-118">**Retry Interval**</span></span>|<span data-ttu-id="517b7-119">アダプターが再試行を開始するまでに待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="517b7-119">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="517b7-120">既定値は、5 分です。</span><span class="sxs-lookup"><span data-stu-id="517b7-120">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="517b7-121">展開して、**サーバー接続の定義**し必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="517b7-121">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="517b7-122">パラメーター</span><span class="sxs-lookup"><span data-stu-id="517b7-122">Parameter</span></span>|<span data-ttu-id="517b7-123">Description</span><span class="sxs-lookup"><span data-stu-id="517b7-123">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="517b7-124">**変換先**</span><span class="sxs-lookup"><span data-stu-id="517b7-124">**Destination**</span></span>|<span data-ttu-id="517b7-125">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="517b7-125">Mandatory setting.</span></span> <span data-ttu-id="517b7-126">送信先の名前と種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="517b7-126">Defines the name and type of the destination.</span></span> <span data-ttu-id="517b7-127">キューまたはトピックを Queue[queue.name] または Topic[topic.name] という形式で定義します。</span><span class="sxs-lookup"><span data-stu-id="517b7-127">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="517b7-128">**[ポート番号]**</span><span class="sxs-lookup"><span data-stu-id="517b7-128">**Port Number**</span></span>|<span data-ttu-id="517b7-129">TIBCO EMS サーバーがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="517b7-129">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="517b7-130">**[サーバー名]**</span><span class="sxs-lookup"><span data-stu-id="517b7-130">**Server Name**</span></span>|<span data-ttu-id="517b7-131">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="517b7-131">Mandatory setting.</span></span> <span data-ttu-id="517b7-132">TIBCO EMS サーバーをホストしているシステムの名前です。</span><span class="sxs-lookup"><span data-stu-id="517b7-132">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="517b7-133">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="517b7-133">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="517b7-134">TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="517b7-134">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="517b7-135">資格情報 (ユーザー名とパスワードのパラメーター) を使用するまたはシングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="517b7-135">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="517b7-136">選択**はい**で**SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="517b7-136">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="517b7-137">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="517b7-137">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="517b7-138">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="517b7-138">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="517b7-139">Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="517b7-139">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="517b7-140">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="517b7-140">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="517b7-141">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。</span><span class="sxs-lookup"><span data-stu-id="517b7-141">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="517b7-142">展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="517b7-142">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="517b7-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="517b7-143">Parameter</span></span>|<span data-ttu-id="517b7-144">Description</span><span class="sxs-lookup"><span data-stu-id="517b7-144">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="517b7-145">TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="517b7-145">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="517b7-146">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="517b7-146">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="517b7-147">TIBCO EMS デーモンとの通信に使用するユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="517b7-147">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="517b7-148">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="517b7-148">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="517b7-149">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="517b7-149">Click **Apply**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517b7-150">参照</span><span class="sxs-lookup"><span data-stu-id="517b7-150">See Also</span></span>  
 <span data-ttu-id="517b7-151">[送信ポートの作成](../core/creating-send-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="517b7-151">[Creating Send Ports](../core/creating-send-ports1.md) </span></span>  
 [<span data-ttu-id="517b7-152">TIBCO Enterprise Message Service を作成する受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="517b7-152">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)