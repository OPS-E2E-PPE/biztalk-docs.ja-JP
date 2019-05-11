---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 856309a744d1874d336bb31840f193494858c81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393294"
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a><span data-ttu-id="60b55-101">TIBCO Enterprise Message Service 受信ポートのトランスポート プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="60b55-101">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>
<span data-ttu-id="60b55-102">TIBCO Enterprise Message System (EMS) の受信場所、 **URL**と**Target Namespace** TIBCO EMS システムには必要な唯一の構成値。</span><span class="sxs-lookup"><span data-stu-id="60b55-102">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>  
  
### <a name="to-specify-tibco-ems-transport-properties"></a><span data-ttu-id="60b55-103">TIBCO EMS トランスポートのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="60b55-103">To specify TIBCO EMS transport properties</span></span>  
  
1.  <span data-ttu-id="60b55-104">展開、**システム定義**し、TIBCO EMS サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="60b55-104">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="60b55-105">展開**メッセージの処理**必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="60b55-105">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="60b55-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60b55-106">Parameter</span></span>|<span data-ttu-id="60b55-107">説明</span><span class="sxs-lookup"><span data-stu-id="60b55-107">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="60b55-108">**メッセージ セレクター**</span><span class="sxs-lookup"><span data-stu-id="60b55-108">**Message Selector**</span></span>|<span data-ttu-id="60b55-109">メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。</span><span class="sxs-lookup"><span data-stu-id="60b55-109">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="60b55-110">受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。</span><span class="sxs-lookup"><span data-stu-id="60b55-110">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="60b55-111">メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="60b55-111">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="60b55-112">構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="60b55-112">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="60b55-113">たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="60b55-113">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="60b55-114">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="60b55-114">**Retry Count**</span></span>|<span data-ttu-id="60b55-115">トランスポートの再試行の回数です。</span><span class="sxs-lookup"><span data-stu-id="60b55-115">The retry count for the transport.</span></span> <span data-ttu-id="60b55-116">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="60b55-116">Default value is 0.</span></span>|  
    |<span data-ttu-id="60b55-117">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="60b55-117">**Retry Interval**</span></span>|<span data-ttu-id="60b55-118">アダプターが再試行を開始するまでに待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="60b55-118">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="60b55-119">既定値は、5 分です。</span><span class="sxs-lookup"><span data-stu-id="60b55-119">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="60b55-120">展開、**サーバー接続の定義**必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="60b55-120">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="60b55-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60b55-121">Parameter</span></span>|<span data-ttu-id="60b55-122">説明</span><span class="sxs-lookup"><span data-stu-id="60b55-122">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="60b55-123">**変換先**</span><span class="sxs-lookup"><span data-stu-id="60b55-123">**Destination**</span></span>|<span data-ttu-id="60b55-124">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="60b55-124">Mandatory setting.</span></span> <span data-ttu-id="60b55-125">送信先の名前と種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="60b55-125">Defines the name and type of the destination.</span></span> <span data-ttu-id="60b55-126">次の形式でキューまたはトピックを定義します。Queue[queue.name] または Topic[topic.name]。</span><span class="sxs-lookup"><span data-stu-id="60b55-126">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="60b55-127">**[ポート番号]**</span><span class="sxs-lookup"><span data-stu-id="60b55-127">**Port Number**</span></span>|<span data-ttu-id="60b55-128">TIBCO EMS サーバーがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="60b55-128">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="60b55-129">**[サーバー名]**</span><span class="sxs-lookup"><span data-stu-id="60b55-129">**Server Name**</span></span>|<span data-ttu-id="60b55-130">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="60b55-130">Mandatory setting.</span></span> <span data-ttu-id="60b55-131">TIBCO EMS サーバーをホストしているシステムの名前です。</span><span class="sxs-lookup"><span data-stu-id="60b55-131">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="60b55-132">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="60b55-132">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="60b55-133">TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b55-133">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="60b55-134">資格情報 (ユーザー名とパスワードのパラメーター) を使用するか、シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="60b55-134">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="60b55-135">選択**はい**で**を使用して SSO**でシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="60b55-135">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="60b55-136">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="60b55-136">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="60b55-137">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="60b55-137">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="60b55-138">Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b55-138">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="60b55-139">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="60b55-139">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="60b55-140">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。</span><span class="sxs-lookup"><span data-stu-id="60b55-140">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="60b55-141">展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="60b55-141">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="60b55-142">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60b55-142">Parameter</span></span>|<span data-ttu-id="60b55-143">説明</span><span class="sxs-lookup"><span data-stu-id="60b55-143">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="60b55-144">TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="60b55-144">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="60b55-145">選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b55-145">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="60b55-146">TIBCO EMS デーモンとの通信に使用するユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="60b55-146">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="60b55-147">選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b55-147">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="60b55-148">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="60b55-148">Click **Apply**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b55-149">参照</span><span class="sxs-lookup"><span data-stu-id="60b55-149">See Also</span></span>  
  [<span data-ttu-id="60b55-150">TIBCO Enterprise Message Service 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="60b55-150">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)