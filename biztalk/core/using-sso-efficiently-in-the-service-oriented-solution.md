---
title: "サービスの SSO の効率的な使用指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a><span data-ttu-id="d1baf-102">指向ソリューションのサービスで SSO の効率的な使用</span><span class="sxs-lookup"><span data-stu-id="d1baf-102">Using SSO Efficiently in the Service Oriented Solution</span></span>
<span data-ttu-id="d1baf-103">サービス指向ソリューションでは、バックエンド システムの構成値の保存と資格情報の処理にエンタープライズ シングル サインオン (SSO) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-103">The service oriented solution uses Enterprise Single Sign-On (SSO) both to store configuration values and to handle credentials for the back-end systems.</span></span> <span data-ttu-id="d1baf-104">待機時間を減らすために、このソリューションでは構成値のローカル キャッシュが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-104">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="d1baf-105">キャッシュは 5 分おきに更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-105">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="d1baf-106">多くのアプリケーションでは、SSO チケットの取得、チケットの引き換え、関連アプリケーションにアクセスするための資格情報の使用をはじめとする SSO 操作をアダプタで処理します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-106">In many applications, the adapters handle the SSO operations—including getting an SSO ticket, redeeming the ticket, and using the credentials to gain access to the affiliate application.</span></span> <span data-ttu-id="d1baf-107">しかし、サービス指向ソリューションのインライン バージョンはアダプタを使用しないので、</span><span class="sxs-lookup"><span data-stu-id="d1baf-107">However, the inline version of the service oriented solution does not use adapters.</span></span> <span data-ttu-id="d1baf-108">コードから SSO を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-108">It must use SSO from code.</span></span>  
  
 <span data-ttu-id="d1baf-109">このトピックでは、ソリューションが使用するキャッシュのメカニズムと、ソリューションのインライン バージョンがコードから SSO を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-109">This topic describes the caching mechanism used by the solution, as well as how the inline version of the solution uses SSO from code.</span></span>  
  
## <a name="local-caching-of-configuration-values"></a><span data-ttu-id="d1baf-110">構成値のローカル キャッシュ</span><span class="sxs-lookup"><span data-stu-id="d1baf-110">Local Caching of Configuration Values</span></span>  
 <span data-ttu-id="d1baf-111">サービス指向ソリューションは 2 つのオブジェクトを使用して**ConfigPropertyBag**と**ConfigParameters**構成値を処理します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-111">The service oriented solution uses two objects, **ConfigPropertyBag** and **ConfigParameters**, to handle the configuration values.</span></span> <span data-ttu-id="d1baf-112">**ConfigPropertyBag**クラス、値を保持およびのみで使用される、 **ConfigParameters**クラスです。</span><span class="sxs-lookup"><span data-stu-id="d1baf-112">The **ConfigPropertyBag** class holds the values and is used only by the **ConfigParameters** class.</span></span> <span data-ttu-id="d1baf-113">**ConfigParameters**クラスは、構成パラメーターを取得するソリューションの他の部分で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-113">The **ConfigParameters** class is used by the other parts of the solution to retrieve the configuration parameters.</span></span> <span data-ttu-id="d1baf-114">クラスは両方の**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**名前空間。</span><span class="sxs-lookup"><span data-stu-id="d1baf-114">Both classes are in the **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1baf-115">サービス指向ソリューションではキャッシュ更新間隔が 300 秒 (5 分) に固定されます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-115">The Service Oriented solution fixes the cache refresh interval at 300 seconds (5 minutes).</span></span> <span data-ttu-id="d1baf-116">ただし、このソリューションでキャッシュ更新間隔を構成可能なプロパティにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-116">You may, instead, want to make the cache refresh interval itself  a configurable property in this solution.</span></span> <span data-ttu-id="d1baf-117">この設定はビジネス プロセス管理ソリューションで行います。</span><span class="sxs-lookup"><span data-stu-id="d1baf-117">This is done in the Business Process Management solution.</span></span> <span data-ttu-id="d1baf-118">そのソリューションが SSO を処理する方法の詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="d1baf-118">For more information about how that solution handles SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span> <span data-ttu-id="d1baf-119">なお、更新間隔を変更した場合は、以前の間隔で最後にキャッシュが更新された後で変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-119">Notice that, in such a case, a change in the refresh interval does not take effect until the cache is refreshed at the end of the old interval time.</span></span>  
  
 <span data-ttu-id="d1baf-120">**ConfigPropertyBag**次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-120">The **ConfigPropertyBag** has the following methods:</span></span>  
  
|<span data-ttu-id="d1baf-121">方法</span><span class="sxs-lookup"><span data-stu-id="d1baf-121">Method</span></span>|<span data-ttu-id="d1baf-122">Description</span><span class="sxs-lookup"><span data-stu-id="d1baf-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d1baf-123">読み取り</span><span class="sxs-lookup"><span data-stu-id="d1baf-123">Read</span></span>|<span data-ttu-id="d1baf-124">指定したプロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-124">Retrieves a value for a given property.</span></span>|  
|<span data-ttu-id="d1baf-125">Write</span><span class="sxs-lookup"><span data-stu-id="d1baf-125">Write</span></span>|<span data-ttu-id="d1baf-126">値をプロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-126">Assigns a value to a property.</span></span>|  
  
 <span data-ttu-id="d1baf-127">.NET のインスタンスを使用するクラス**NameValueCollection**値を保持します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-127">The class uses an instance of a .NET **NameValueCollection** to hold the values.</span></span> <span data-ttu-id="d1baf-128">2 つのアクセス メソッドを実装、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**名前空間。</span><span class="sxs-lookup"><span data-stu-id="d1baf-128">The two access methods implement the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace.</span></span> <span data-ttu-id="d1baf-129">**ConfigPropertyBag**クラスは、内部とクラスだけで使用される、 **ConfigParameters**クラスです。</span><span class="sxs-lookup"><span data-stu-id="d1baf-129">The **ConfigPropertyBag** class is an internal class and used only by the **ConfigParameters** class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1baf-130">プロパティ バッグのキー名は大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="d1baf-130">Key names in the property bag are case insensitive.</span></span> <span data-ttu-id="d1baf-131">基になる**NameValueCollection**ハッシュの大文字と小文字の比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-131">The underlying **NameValueCollection** uses case-insensitive hashing and case-insensitive comparisons.</span></span>  
  
 <span data-ttu-id="d1baf-132">アプリケーションを使用して、 **ConfigParameters** SSO 構成値を処理するクラス。</span><span class="sxs-lookup"><span data-stu-id="d1baf-132">The application uses the **ConfigParameters** class to handle the SSO configuration values.</span></span> <span data-ttu-id="d1baf-133">このクラスには、次のパブリック メソッドと属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-133">The class has the following public methods and attributes:</span></span>  
  
|<span data-ttu-id="d1baf-134">メソッドまたは属性</span><span class="sxs-lookup"><span data-stu-id="d1baf-134">Method or Attribute</span></span>|<span data-ttu-id="d1baf-135">Description</span><span class="sxs-lookup"><span data-stu-id="d1baf-135">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="d1baf-136">SSOConfigParameter</span><span class="sxs-lookup"><span data-stu-id="d1baf-136">SSOConfigParameter</span></span>|<span data-ttu-id="d1baf-137">構成パラメータを指定する列挙。</span><span class="sxs-lookup"><span data-stu-id="d1baf-137">An enumeration for specifying configuration parameters.</span></span>|  
|<span data-ttu-id="d1baf-138">GetConfigParameters</span><span class="sxs-lookup"><span data-stu-id="d1baf-138">GetConfigParameters</span></span>|<span data-ttu-id="d1baf-139">特定のパラメータの値を取得するメソッド。</span><span class="sxs-lookup"><span data-stu-id="d1baf-139">A method used to retrieve a value for a given parameter.</span></span> <span data-ttu-id="d1baf-140">SSOConfigParameter を使用してパラメータを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-140">Uses the SSOConfigParameter to indicate the parameter.</span></span>|  
  
 <span data-ttu-id="d1baf-141">**ConfigParameters**クラスは .NET Timer クラスとデリゲート関数の更新設定を使って、 **ConfigPropertyBag**:</span><span class="sxs-lookup"><span data-stu-id="d1baf-141">The **ConfigParameters** class uses the .NET Timer class and a delegate function to set up the refresh of the **ConfigPropertyBag**:</span></span>  
  
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
  
 <span data-ttu-id="d1baf-142">この静的コンストラクタにより静的メンバの変数が初期化されるので、クラスのインスタンスを作成しなくてもクラス メソッドが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-142">Notice that the static constructor initializes the static member variables thus enabling the use of class methods without creating an instance of the class.</span></span> <span data-ttu-id="d1baf-143">コンス トラクターは、SSO 構成ストアのインスタンスを作成する (**ISSOConfigStore**)、構成プロパティ バッグ (**ConfigPropertyBag**)、および同期ロック (**ReaderWriterLock**) へのアクセスを制御するために使用、 **ConfigurationPropertyBag**更新と読み取り中にします。</span><span class="sxs-lookup"><span data-stu-id="d1baf-143">The constructor creates instances of the SSO configuration store (**ISSOConfigStore**), the configuration property bag (**ConfigPropertyBag**), and a synchronization lock (**ReaderWriterLock**) used to control access to the **ConfigurationPropertyBag** during updates and reads.</span></span> <span data-ttu-id="d1baf-144">コンス トラクターを使用し、 **GetConfigInfo** SSO 構成値を取得し、プロパティ バッグに格納します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-144">The constructor then uses **GetConfigInfo** to retrieve the SSO configuration values and to put them in the property bag.</span></span> <span data-ttu-id="d1baf-145">最後に、コンス トラクターは、作成、**タイマー** 、一定の間隔の後に、デリゲート関数を呼び出すオブジェクト**cacheRefreshCallback**です。</span><span class="sxs-lookup"><span data-stu-id="d1baf-145">Finally, the constructor creates a **Timer** object that, after the specified interval, calls the delegate function, **cacheRefreshCallback**.</span></span>  
  
 <span data-ttu-id="d1baf-146">**タイマー**デリゲート関数は比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="d1baf-146">The **Timer** delegate function is relatively straightforward:</span></span>  
  
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
  
 <span data-ttu-id="d1baf-147">キャッシュ更新コールバック メソッドは、メソッドが最後まで実行されるように、タイマを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1baf-147">Notice that the cache refresh callback method disables the timer so that the method can run all the way through.</span></span> <span data-ttu-id="d1baf-148">また、ロックの使用によってプロパティ バッグへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-148">Also notice the use of the locks to control access to the property bag.</span></span> <span data-ttu-id="d1baf-149">**ReaderWriterLock**最適な選択肢をここでは、— のケースのものでは書き込みより読み取りができます。</span><span class="sxs-lookup"><span data-stu-id="d1baf-149">The **ReaderWriterLock** is the best choice here—it is designed for cases where there are more reads than writes.</span></span> <span data-ttu-id="d1baf-150">注意しても、ロック**syncLock**が静的では、レベルのすべてのスレッドがその同じ、1 つのインスタンスを共有するクラスで宣言されています。</span><span class="sxs-lookup"><span data-stu-id="d1baf-150">Notice also that the lock, **syncLock**, is static and declared at the class level that all threads share the same, single instance of it.</span></span>  
  
## <a name="using-sso-from-code"></a><span data-ttu-id="d1baf-151">コードからの SSO の使用</span><span class="sxs-lookup"><span data-stu-id="d1baf-151">Using SSO from Code</span></span>  
 <span data-ttu-id="d1baf-152">アダプターの役割に、コードを受け取る必要がありますコードからシングル サインオンを使用する場合。 つまり、メッセージから SSO チケットを取得、バックエンド システムのユーザー名とパスワードを取得するチケットを引き換えると、最後に、バックエンド システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-152">When using single sign-on from code, the code must take on the role of the adapter: that is,retrieve the SSO ticket from the message, redeem the ticket to get the user name and password for the back-end system, and, finally, use the back-end system.</span></span> <span data-ttu-id="d1baf-153">サービス指向ソリューションはこれを**GetPendingTransactionsResponse**のメソッド、 **PendingTransactionsCaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d1baf-153">The service-oriented solution does this through the **GetPendingTransactionsResponse** method of the **PendingTransactionsCaller** object.</span></span>  
  
 <span data-ttu-id="d1baf-154">メソッドの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1baf-154">The method appears as follows:</span></span>  
  
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
  
 <span data-ttu-id="d1baf-155">このメソッドではまず、バックエンド システムの URL やバックエンド (関連) アプリケーションの名前などの構成情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="d1baf-155">The method begins by retrieving configuration information, including the URL, for the back-end system and the name of the backend (affiliate) application.</span></span>  
  
 <span data-ttu-id="d1baf-156">チケットを引き換えるために、メソッドはメッセージからチケットと元の要求ユーザー名を抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-156">To redeem the ticket, the method must extract the ticket and original requesting user name from the message.</span></span> <span data-ttu-id="d1baf-157">メッセージには、メッセージ コンテキスト プロパティの 1 つとしてチケットが含まれる**BTS です。SSOTicket**です。</span><span class="sxs-lookup"><span data-stu-id="d1baf-157">The message contains the ticket as one of the message context properties, **BTS.SSOTicket**.</span></span> <span data-ttu-id="d1baf-158">詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d1baf-158">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="d1baf-159">メソッドの抽出も、 **OriginatorSID**メッセージ コンテキスト プロパティからです。</span><span class="sxs-lookup"><span data-stu-id="d1baf-159">The method also extracts the **OriginatorSID** from the message context properties.</span></span> <span data-ttu-id="d1baf-160">メソッドは、抽出したチケットと発信者の名前を使用して、チケットに対して RedeemTicket メソッドを呼び出し、資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1baf-160">With the ticket and the originator's name in hand, the method calls the RedeemTicket method on the ticket to retrieve the credentials.</span></span>  
  
 <span data-ttu-id="d1baf-161">残りのコードでは、資格情報の .NET NetworkCredential キャッシュを作成してバックエンド Web サービスを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="d1baf-161">The remainder of the code creates a .NET NetworkCredential cache for the credentials and calls the back-end Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1baf-162">ユーザー名とパスワードは SSO からクリアテキストで返されるので、その情報が変数に保持されている時間は最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1baf-162">Because the user name and password come back from SSO in clear text, you want to minimize the lifetime of variables holding that information.</span></span> <span data-ttu-id="d1baf-163">コードが内で資格情報の変数を宣言することに注意してください、**再試行**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="d1baf-163">Notice that the code declares the credential variables within a **try** block.</span></span> <span data-ttu-id="d1baf-164">終了時に変数がここでは、期限切れ、**再試行**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="d1baf-164">Here, the variables expire upon exit from the **try** block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1baf-165">参照</span><span class="sxs-lookup"><span data-stu-id="d1baf-165">See Also</span></span>  
 [<span data-ttu-id="d1baf-166">指向ソリューションのサービスの実装の要点</span><span class="sxs-lookup"><span data-stu-id="d1baf-166">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)