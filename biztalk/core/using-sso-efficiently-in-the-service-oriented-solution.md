---
title: サービスで効率的に SSO を使用して指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e5f411ff3bc003966e001fa44c559a803bba991
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321589"
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a><span data-ttu-id="9f89d-102">サービスで効率的に SSO を使用して指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="9f89d-102">Using SSO Efficiently in the Service Oriented Solution</span></span>
<span data-ttu-id="9f89d-103">サービス指向ソリューションは、構成値を保存し、バックエンド システム用の資格情報を処理するために、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-103">The service oriented solution uses Enterprise Single Sign-On (SSO) both to store configuration values and to handle credentials for the back-end systems.</span></span> <span data-ttu-id="9f89d-104">待機時間を減らすためには、ソリューションは構成値のローカル キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-104">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="9f89d-105">ソリューションは、5 分ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-105">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="9f89d-106">アダプターが SSO 操作を処理する多くのアプリケーションで、SSO チケットの取得、チケットの引き換え、関連アプリケーションにアクセスする資格情報を使用してなど。</span><span class="sxs-lookup"><span data-stu-id="9f89d-106">In many applications, the adapters handle the SSO operations—including getting an SSO ticket, redeeming the ticket, and using the credentials to gain access to the affiliate application.</span></span> <span data-ttu-id="9f89d-107">ただし、サービス指向ソリューションのインライン バージョンでは、アダプターは使用しません。</span><span class="sxs-lookup"><span data-stu-id="9f89d-107">However, the inline version of the service oriented solution does not use adapters.</span></span> <span data-ttu-id="9f89d-108">SSO を使用して、コードからその必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f89d-108">It must use SSO from code.</span></span>  
  
 <span data-ttu-id="9f89d-109">このトピックは、ソリューションのインライン バージョンは、コードから SSO を使用する方法も、ソリューションで使用されるキャッシュ メカニズムを示します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-109">This topic describes the caching mechanism used by the solution, as well as how the inline version of the solution uses SSO from code.</span></span>  
  
## <a name="local-caching-of-configuration-values"></a><span data-ttu-id="9f89d-110">構成値のローカル キャッシュ</span><span class="sxs-lookup"><span data-stu-id="9f89d-110">Local Caching of Configuration Values</span></span>  
 <span data-ttu-id="9f89d-111">サービス指向ソリューションは 2 つのオブジェクトを使用して**ConfigPropertyBag**と**ConfigParameters**構成値を処理します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-111">The service oriented solution uses two objects, **ConfigPropertyBag** and **ConfigParameters**, to handle the configuration values.</span></span> <span data-ttu-id="9f89d-112">**ConfigPropertyBag**クラスの値を保持およびのみで使用される、 **ConfigParameters**クラス。</span><span class="sxs-lookup"><span data-stu-id="9f89d-112">The **ConfigPropertyBag** class holds the values and is used only by the **ConfigParameters** class.</span></span> <span data-ttu-id="9f89d-113">**ConfigParameters**クラスは、構成パラメーターを取得するソリューションの他の部分によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f89d-113">The **ConfigParameters** class is used by the other parts of the solution to retrieve the configuration parameters.</span></span> <span data-ttu-id="9f89d-114">クラスは両方、 **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**名前空間。</span><span class="sxs-lookup"><span data-stu-id="9f89d-114">Both classes are in the **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f89d-115">サービス指向ソリューションでは、300 秒 (5 分) で、キャッシュ更新間隔を修正します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-115">The Service Oriented solution fixes the cache refresh interval at 300 seconds (5 minutes).</span></span> <span data-ttu-id="9f89d-116">このソリューションで構成可能なプロパティ自体キャッシュ更新間隔を作成することが代わりに、します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-116">You may, instead, want to make the cache refresh interval itself  a configurable property in this solution.</span></span> <span data-ttu-id="9f89d-117">これは、ビジネス プロセス管理ソリューションで行われます。</span><span class="sxs-lookup"><span data-stu-id="9f89d-117">This is done in the Business Process Management solution.</span></span> <span data-ttu-id="9f89d-118">そのソリューションが SSO を処理する方法の詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-118">For more information about how that solution handles SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span> <span data-ttu-id="9f89d-119">このような場合は、更新間隔の変更は反映されません古い時間間隔の最後に、キャッシュが更新されるまでに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f89d-119">Notice that, in such a case, a change in the refresh interval does not take effect until the cache is refreshed at the end of the old interval time.</span></span>  
  
 <span data-ttu-id="9f89d-120">**ConfigPropertyBag**次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="9f89d-120">The **ConfigPropertyBag** has the following methods:</span></span>  
  
|<span data-ttu-id="9f89d-121">方法</span><span class="sxs-lookup"><span data-stu-id="9f89d-121">Method</span></span>|<span data-ttu-id="9f89d-122">説明</span><span class="sxs-lookup"><span data-stu-id="9f89d-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9f89d-123">Read</span><span class="sxs-lookup"><span data-stu-id="9f89d-123">Read</span></span>|<span data-ttu-id="9f89d-124">特定のプロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-124">Retrieves a value for a given property.</span></span>|  
|<span data-ttu-id="9f89d-125">書き込み</span><span class="sxs-lookup"><span data-stu-id="9f89d-125">Write</span></span>|<span data-ttu-id="9f89d-126">プロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9f89d-126">Assigns a value to a property.</span></span>|  
  
 <span data-ttu-id="9f89d-127">クラスは、.NET のインスタンスを使用して**NameValueCollection**値を保持します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-127">The class uses an instance of a .NET **NameValueCollection** to hold the values.</span></span> <span data-ttu-id="9f89d-128">2 つのアクセス メソッドの実装、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**名前空間。</span><span class="sxs-lookup"><span data-stu-id="9f89d-128">The two access methods implement the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace.</span></span> <span data-ttu-id="9f89d-129">**ConfigPropertyBag**クラスは内部クラスでありでのみ使用、 **ConfigParameters**クラス。</span><span class="sxs-lookup"><span data-stu-id="9f89d-129">The **ConfigPropertyBag** class is an internal class and used only by the **ConfigParameters** class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f89d-130">プロパティ バッグ内のキー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-130">Key names in the property bag are case insensitive.</span></span> <span data-ttu-id="9f89d-131">基になる**NameValueCollection**ハッシュの大文字と小文字の比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-131">The underlying **NameValueCollection** uses case-insensitive hashing and case-insensitive comparisons.</span></span>  
  
 <span data-ttu-id="9f89d-132">アプリケーションを使用して、 **ConfigParameters** SSO の構成値を処理するクラス。</span><span class="sxs-lookup"><span data-stu-id="9f89d-132">The application uses the **ConfigParameters** class to handle the SSO configuration values.</span></span> <span data-ttu-id="9f89d-133">クラスには、次のパブリック メソッドと属性があります。</span><span class="sxs-lookup"><span data-stu-id="9f89d-133">The class has the following public methods and attributes:</span></span>  
  
|<span data-ttu-id="9f89d-134">メソッドまたは属性</span><span class="sxs-lookup"><span data-stu-id="9f89d-134">Method or Attribute</span></span>|<span data-ttu-id="9f89d-135">説明</span><span class="sxs-lookup"><span data-stu-id="9f89d-135">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="9f89d-136">SSOConfigParameter</span><span class="sxs-lookup"><span data-stu-id="9f89d-136">SSOConfigParameter</span></span>|<span data-ttu-id="9f89d-137">構成パラメーターを指定する列挙です。</span><span class="sxs-lookup"><span data-stu-id="9f89d-137">An enumeration for specifying configuration parameters.</span></span>|  
|<span data-ttu-id="9f89d-138">GetConfigParameters</span><span class="sxs-lookup"><span data-stu-id="9f89d-138">GetConfigParameters</span></span>|<span data-ttu-id="9f89d-139">特定のパラメーターの値を取得するために使用するメソッド。</span><span class="sxs-lookup"><span data-stu-id="9f89d-139">A method used to retrieve a value for a given parameter.</span></span> <span data-ttu-id="9f89d-140">SSOConfigParameter を使用して、パラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-140">Uses the SSOConfigParameter to indicate the parameter.</span></span>|  
  
 <span data-ttu-id="9f89d-141">**ConfigParameters**クラスの更新を設定する、.NET タイマー クラスとデリゲート関数を使用して、 **ConfigPropertyBag**:</span><span class="sxs-lookup"><span data-stu-id="9f89d-141">The **ConfigParameters** class uses the .NET Timer class and a delegate function to set up the refresh of the **ConfigPropertyBag**:</span></span>  
  
```  
private static Timer cacheRefreshTimer;  
private static ISSOConfigStore ssoConfigStore;  
private static ReaderWriterLock syncLock;  
  
// Cache refresh interval in milliseconds  
private const int CacheRefreshInterval = 5 * 60 * 1000;  
private static ConfigPropertyBag ssoPropBag;  
  
static ConfigParameters()  
{  
    ssoConfigStore = new ISSOConfigStore();  
    ssoPropBag = new ConfigPropertyBag();  
    syncLock = new ReaderWriterLock();  
  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,  
         SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME,  
         ssoPropBag);  
  
    cacheRefreshTimer = new Timer(  
        new TimerCallback(ConfigParameters.cacheRefreshCallback),  
        null, CacheRefreshInterval, CacheRefreshInterval);  
}  
```  
  
 <span data-ttu-id="9f89d-142">静的コンス トラクターがクラスのインスタンスを作成せずクラスのメソッドを使用できるように、静的メンバー変数を初期化することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-142">Notice that the static constructor initializes the static member variables thus enabling the use of class methods without creating an instance of the class.</span></span> <span data-ttu-id="9f89d-143">コンス トラクターは、SSO 構成ストアのインスタンスを作成します (**ISSOConfigStore**)、構成プロパティ バッグ (**ConfigPropertyBag**)、および同期ロック (**ReaderWriterLock**) へのアクセスを制御するために使用、 **ConfigurationPropertyBag**更新と読み取り中にします。</span><span class="sxs-lookup"><span data-stu-id="9f89d-143">The constructor creates instances of the SSO configuration store (**ISSOConfigStore**), the configuration property bag (**ConfigPropertyBag**), and a synchronization lock (**ReaderWriterLock**) used to control access to the **ConfigurationPropertyBag** during updates and reads.</span></span> <span data-ttu-id="9f89d-144">コンス トラクターを使用し、 **GetConfigInfo** SSO 構成値を取得して、プロパティ バッグに格納します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-144">The constructor then uses **GetConfigInfo** to retrieve the SSO configuration values and to put them in the property bag.</span></span> <span data-ttu-id="9f89d-145">最後に、コンス トラクターを作成、**タイマー** 、一定の間隔の後に、デリゲート関数を呼び出すオブジェクト**cacheRefreshCallback**します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-145">Finally, the constructor creates a **Timer** object that, after the specified interval, calls the delegate function, **cacheRefreshCallback**.</span></span>  
  
 <span data-ttu-id="9f89d-146">**タイマー**デリゲート関数は比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="9f89d-146">The **Timer** delegate function is relatively straightforward:</span></span>  
  
```  
private static void cacheRefreshCallback(object state)  
{  
    // Disable the timer until we are done loading the cache.  
    cacheRefreshTimer.Change(Timeout.Infinite, CacheRefreshInterval);  
  
    // Put the data from SSO in a new property bag so that  
    // we don't have to lock the property bag and block it from being  
    // used. The SSO call is a remote call and may take a while.  
    ConfigPropertyBag propBag2 = new ConfigPropertyBag();  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,   
        SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME, propBag2);  
  
    // Get a writer lock before updating the cached values.  
    syncLock.AcquireWriterLock(Timeout.Infinite);  
  
    try  
    {  
        ssoPropBag = propBag2;  
    }  
    finally   
    {  
        syncLock.ReleaseWriterLock();  
    }  
    // Enable the timer.  
    cacheRefreshTimer.Change(CacheRefreshInterval,   
        CacheRefreshInterval);  
}  
```  
  
 <span data-ttu-id="9f89d-147">メソッドは最後まで実行できるように、キャッシュ更新コールバック メソッドが、タイマーを無効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-147">Notice that the cache refresh callback method disables the timer so that the method can run all the way through.</span></span> <span data-ttu-id="9f89d-148">また、プロパティ バッグへのアクセスを制御するロックの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f89d-148">Also notice the use of the locks to control access to the property bag.</span></span> <span data-ttu-id="9f89d-149">**ReaderWriterLock**最適な選択肢をここでは、-ケース用に設計されていますが書き込みより読み取りがある場合。</span><span class="sxs-lookup"><span data-stu-id="9f89d-149">The **ReaderWriterLock** is the best choice here—it is designed for cases where there are more reads than writes.</span></span> <span data-ttu-id="9f89d-150">また、ロック**syncLock**が静的では、レベルのすべてのスレッドがその同じ、1 つのインスタンスを共有する、クラスで宣言します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-150">Notice also that the lock, **syncLock**, is static and declared at the class level that all threads share the same, single instance of it.</span></span>  
  
## <a name="using-sso-from-code"></a><span data-ttu-id="9f89d-151">コードから SSO を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9f89d-151">Using SSO from Code</span></span>  
 <span data-ttu-id="9f89d-152">アダプターの役割に、コードを実行する必要がありますコードからシングル サインオンを使用する場合。 つまり、メッセージから SSO チケットを取得、バックエンド システムでは、ユーザー名とパスワードを取得するチケットを引き換えると、最後に、バックエンド システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-152">When using single sign-on from code, the code must take on the role of the adapter: that is,retrieve the SSO ticket from the message, redeem the ticket to get the user name and password for the back-end system, and, finally, use the back-end system.</span></span> <span data-ttu-id="9f89d-153">サービス指向ソリューションはこれを**GetPendingTransactionsResponse**のメソッド、 **PendingTransactionsCaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9f89d-153">The service-oriented solution does this through the **GetPendingTransactionsResponse** method of the **PendingTransactionsCaller** object.</span></span>  
  
 <span data-ttu-id="9f89d-154">メソッドは次のようです。</span><span class="sxs-lookup"><span data-stu-id="9f89d-154">The method appears as follows:</span></span>  
  
```  
public static PendingTransactionsResponse GetPendingTransactionsResponse(XLANGMessage requestMsg)  
{  
    try  
    {  
        // Get config parameter values.  
        int ptTimeout = Convert.ToInt32(  
            ConfigParameters.GetConfigParameter(  
                ConfigParameters.  
                    SSOConfigParameter.  
                        PENDING_TRANSACTIONS_INLINE_TIMEOUT  
            )  
        );  
  
        string ptURL = ConfigParameters.GetConfigParameter(  
            ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_URL  
        );  
        string ssoAffliateApp = ConfigParameters.  
            GetConfigParameter(ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_SSO_AFFILIATE_APP  
            );  
  
        // Redeem the SSO ticket and get the userid/password to   
        // use to interact with Pending Transaction System.  
  
        // Extract the ticket…  
        string msgTicket = (string)requestMsg.  
            GetPropertyValue(typeof(BTS.SSOTicket));  
  
        // and the user name of the originating user.  
        string originatorSID = (string)requestMsg.  
            GetPropertyValue(  
                typeof(  
                    Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID  
                )  
            );  
  
        string pendTransUserName;  
        // Now, redeem the ticket.  
        string[] pendTransCredential =   
            ssoTicket.RedeemTicket(  
                ssoAffliateApp,  
                originatorSID,  
                msgTicket,  
                SSOFlag.SSO_FLAG_NONE,  
                out pendTransUserName  
            );   
  
        PendingTransactionsRequest req =   
            (PendingTransactionsRequest)requestMsg[0].  
                RetrieveAs(  
                    typeof(PendingTransactionsRequest)  
                );  
        PendingTransactionsResponse resp;  
  
        using (PendingTransactionsWebService  
            svc = new PendingTransactionsWebService())  
        {  
            svc.Url = ptURL;  
            svc.Timeout = ptTimeout;  
  
            // The web service uses basic authentication, so we  
            //need to send the user id and password in the request.  
            CredentialCache credCache = new CredentialCache();  
            NetworkCredential credentialToUse =  
                new NetworkCredential(  
                    pendTransUserName, pendTransCredential[0]  
                );  
            credCache.Add(new Uri(svc.Url), "Basic", credentialToUse);  
            svc.Credentials = credCache;  
  
            resp = svc.GetPendingTransactions(req);  
        }  
        return resp;                  
    }  
    catch (System.Net.WebException webEx)  
    {  
        if (webEx.Status == WebExceptionStatus.Timeout)  
        {  
            throw new PendingTransactionsTimeoutException();  
        }  
        else  
        {  
            Trace.WriteLine("Other Net.WebException: "  
                + webEx.ToString()   
                + (null == webEx.InnerException ? "" :  
                     ("Inner Exception: "   
                        + webEx.InnerException.ToString())  
                )  
            );  
            throw;  
        }  
    }  
    catch(System.Exception ex)  
    {  
        Trace.WriteLine("Other Exception: "  
            + ex.ToString()   
            + (null == ex.InnerException ? "" :   
                 ("Inner Exception: "  
                    + ex.InnerException.ToString())  
                  )  
            );  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="9f89d-155">メソッドは、バックエンド システムとバックエンド (関連) アプリケーションの名前、URL などの構成情報を取得することによって開始します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-155">The method begins by retrieving configuration information, including the URL, for the back-end system and the name of the backend (affiliate) application.</span></span>  
  
 <span data-ttu-id="9f89d-156">チケットを引き換えるに、メソッドは、メッセージからチケットと元の要求元のユーザー名を抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f89d-156">To redeem the ticket, the method must extract the ticket and original requesting user name from the message.</span></span> <span data-ttu-id="9f89d-157">メッセージには、メッセージ コンテキストのプロパティの 1 つとしてチケットが含まれる**BTS します。SSOTicket**します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-157">The message contains the ticket as one of the message context properties, **BTS.SSOTicket**.</span></span> <span data-ttu-id="9f89d-158">詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-158">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="9f89d-159">抽出することも、メソッド、 **OriginatorSID**メッセージ コンテキスト プロパティから。</span><span class="sxs-lookup"><span data-stu-id="9f89d-159">The method also extracts the **OriginatorSID** from the message context properties.</span></span> <span data-ttu-id="9f89d-160">チケットと発信者の名前を使用して、メソッドの呼び出し、資格情報を取得するチケットに対して RedeemTicket メソッド。</span><span class="sxs-lookup"><span data-stu-id="9f89d-160">With the ticket and the originator's name in hand, the method calls the RedeemTicket method on the ticket to retrieve the credentials.</span></span>  
  
 <span data-ttu-id="9f89d-161">コードの残りの部分では、資格情報の .NET NetworkCredential キャッシュを作成し、バックエンドの Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9f89d-161">The remainder of the code creates a .NET NetworkCredential cache for the credentials and calls the back-end Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f89d-162">その情報を保持する変数の有効期間を最小限に抑えたいユーザー名とパスワードが返された SSO からクリア テキストであるためです。</span><span class="sxs-lookup"><span data-stu-id="9f89d-162">Because the user name and password come back from SSO in clear text, you want to minimize the lifetime of variables holding that information.</span></span> <span data-ttu-id="9f89d-163">コード内で資格情報の変数に注意してください、**お試しください**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="9f89d-163">Notice that the code declares the credential variables within a **try** block.</span></span> <span data-ttu-id="9f89d-164">終了時に変数をここでは、期限切れ、**お試しください**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="9f89d-164">Here, the variables expire upon exit from the **try** block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f89d-165">参照</span><span class="sxs-lookup"><span data-stu-id="9f89d-165">See Also</span></span>  
 [<span data-ttu-id="9f89d-166">サービス指向ソリューションの実装の重要なポイント</span><span class="sxs-lookup"><span data-stu-id="9f89d-166">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)