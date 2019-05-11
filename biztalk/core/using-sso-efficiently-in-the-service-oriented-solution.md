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
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a>サービスで効率的に SSO を使用して指向ソリューション
サービス指向ソリューションは、構成値を保存し、バックエンド システム用の資格情報を処理するために、エンタープライズ シングル サインオン (SSO) を使用します。 待機時間を減らすためには、ソリューションは構成値のローカル キャッシュを使用します。 ソリューションは、5 分ごとにキャッシュを更新します。  
  
 アダプターが SSO 操作を処理する多くのアプリケーションで、SSO チケットの取得、チケットの引き換え、関連アプリケーションにアクセスする資格情報を使用してなど。 ただし、サービス指向ソリューションのインライン バージョンでは、アダプターは使用しません。 SSO を使用して、コードからその必要があります。  
  
 このトピックは、ソリューションのインライン バージョンは、コードから SSO を使用する方法も、ソリューションで使用されるキャッシュ メカニズムを示します。  
  
## <a name="local-caching-of-configuration-values"></a>構成値のローカル キャッシュ  
 サービス指向ソリューションは 2 つのオブジェクトを使用して**ConfigPropertyBag**と**ConfigParameters**構成値を処理します。 **ConfigPropertyBag**クラスの値を保持およびのみで使用される、 **ConfigParameters**クラス。 **ConfigParameters**クラスは、構成パラメーターを取得するソリューションの他の部分によって使用されます。 クラスは両方、 **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**名前空間。  
  
> [!NOTE]
>  サービス指向ソリューションでは、300 秒 (5 分) で、キャッシュ更新間隔を修正します。 このソリューションで構成可能なプロパティ自体キャッシュ更新間隔を作成することが代わりに、します。 これは、ビジネス プロセス管理ソリューションで行われます。 そのソリューションが SSO を処理する方法の詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)します。 このような場合は、更新間隔の変更は反映されません古い時間間隔の最後に、キャッシュが更新されるまでに注意してください。  
  
 **ConfigPropertyBag**次の方法があります。  
  
|方法|説明|  
|------------|-----------------|  
|Read|特定のプロパティの値を取得します。|  
|書き込み|プロパティに値を割り当てます。|  
  
 クラスは、.NET のインスタンスを使用して**NameValueCollection**値を保持します。 2 つのアクセス メソッドの実装、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**名前空間。 **ConfigPropertyBag**クラスは内部クラスでありでのみ使用、 **ConfigParameters**クラス。  
  
> [!NOTE]
>  プロパティ バッグ内のキー名は大文字小文字を区別します。 基になる**NameValueCollection**ハッシュの大文字と小文字の比較を使用します。  
  
 アプリケーションを使用して、 **ConfigParameters** SSO の構成値を処理するクラス。 クラスには、次のパブリック メソッドと属性があります。  
  
|メソッドまたは属性|説明|  
|-------------------------|-----------------|  
|SSOConfigParameter|構成パラメーターを指定する列挙です。|  
|GetConfigParameters|特定のパラメーターの値を取得するために使用するメソッド。 SSOConfigParameter を使用して、パラメーターを示します。|  
  
 **ConfigParameters**クラスの更新を設定する、.NET タイマー クラスとデリゲート関数を使用して、 **ConfigPropertyBag**:  
  
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
  
 静的コンス トラクターがクラスのインスタンスを作成せずクラスのメソッドを使用できるように、静的メンバー変数を初期化することを確認します。 コンス トラクターは、SSO 構成ストアのインスタンスを作成します (**ISSOConfigStore**)、構成プロパティ バッグ (**ConfigPropertyBag**)、および同期ロック (**ReaderWriterLock**) へのアクセスを制御するために使用、 **ConfigurationPropertyBag**更新と読み取り中にします。 コンス トラクターを使用し、 **GetConfigInfo** SSO 構成値を取得して、プロパティ バッグに格納します。 最後に、コンス トラクターを作成、**タイマー** 、一定の間隔の後に、デリゲート関数を呼び出すオブジェクト**cacheRefreshCallback**します。  
  
 **タイマー**デリゲート関数は比較的簡単です。  
  
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
  
 メソッドは最後まで実行できるように、キャッシュ更新コールバック メソッドが、タイマーを無効にすることを確認します。 また、プロパティ バッグへのアクセスを制御するロックの使用に注意してください。 **ReaderWriterLock**最適な選択肢をここでは、-ケース用に設計されていますが書き込みより読み取りがある場合。 また、ロック**syncLock**が静的では、レベルのすべてのスレッドがその同じ、1 つのインスタンスを共有する、クラスで宣言します。  
  
## <a name="using-sso-from-code"></a>コードから SSO を使用してください。  
 アダプターの役割に、コードを実行する必要がありますコードからシングル サインオンを使用する場合。 つまり、メッセージから SSO チケットを取得、バックエンド システムでは、ユーザー名とパスワードを取得するチケットを引き換えると、最後に、バックエンド システムを使用します。 サービス指向ソリューションはこれを**GetPendingTransactionsResponse**のメソッド、 **PendingTransactionsCaller**オブジェクト。  
  
 メソッドは次のようです。  
  
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
  
 メソッドは、バックエンド システムとバックエンド (関連) アプリケーションの名前、URL などの構成情報を取得することによって開始します。  
  
 チケットを引き換えるに、メソッドは、メッセージからチケットと元の要求元のユーザー名を抽出する必要があります。 メッセージには、メッセージ コンテキストのプロパティの 1 つとしてチケットが含まれる**BTS します。SSOTicket**します。 詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 抽出することも、メソッド、 **OriginatorSID**メッセージ コンテキスト プロパティから。 チケットと発信者の名前を使用して、メソッドの呼び出し、資格情報を取得するチケットに対して RedeemTicket メソッド。  
  
 コードの残りの部分では、資格情報の .NET NetworkCredential キャッシュを作成し、バックエンドの Web サービスを呼び出します。  
  
> [!NOTE]
>  その情報を保持する変数の有効期間を最小限に抑えたいユーザー名とパスワードが返された SSO からクリア テキストであるためです。 コード内で資格情報の変数に注意してください、**お試しください**ブロックします。 終了時に変数をここでは、期限切れ、**お試しください**ブロックします。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-service-oriented-solution.md)