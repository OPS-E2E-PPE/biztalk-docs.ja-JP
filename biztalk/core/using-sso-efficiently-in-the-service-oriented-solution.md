---
title: サービスの SSO の効率的な使用指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289266"
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a>指向ソリューションのサービスで SSO の効率的な使用
サービス指向ソリューションでは、バックエンド システムの構成値の保存と資格情報の処理にエンタープライズ シングル サインオン (SSO) が使用されます。 待機時間を減らすために、このソリューションでは構成値のローカル キャッシュが使用されます。 キャッシュは 5 分おきに更新されます。  
  
 多くのアプリケーションでは、SSO チケットの取得、チケットの引き換え、関連アプリケーションにアクセスするための資格情報の使用をはじめとする SSO 操作をアダプタで処理します。 しかし、サービス指向ソリューションのインライン バージョンはアダプタを使用しないので、 コードから SSO を使用する必要があります。  
  
 このトピックでは、ソリューションが使用するキャッシュのメカニズムと、ソリューションのインライン バージョンがコードから SSO を使用する方法について説明します。  
  
## <a name="local-caching-of-configuration-values"></a>構成値のローカル キャッシュ  
 サービス指向ソリューションは 2 つのオブジェクトを使用して**ConfigPropertyBag**と**ConfigParameters**構成値を処理します。 **ConfigPropertyBag**クラス、値を保持およびのみで使用される、 **ConfigParameters**クラスです。 **ConfigParameters**クラスは、構成パラメーターを取得するソリューションの他の部分で使用します。 クラスは両方の**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**名前空間。  
  
> [!NOTE]
>  サービス指向ソリューションではキャッシュ更新間隔が 300 秒 (5 分) に固定されます。 ただし、このソリューションでキャッシュ更新間隔を構成可能なプロパティにすることもできます。 この設定はビジネス プロセス管理ソリューションで行います。 そのソリューションが SSO を処理する方法の詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)です。 なお、更新間隔を変更した場合は、以前の間隔で最後にキャッシュが更新された後で変更が有効になります。  
  
 **ConfigPropertyBag**次の方法があります。  
  
|方法|Description|  
|------------|-----------------|  
|読み取り|指定したプロパティの値を取得します。|  
|Write|値をプロパティに割り当てます。|  
  
 .NET のインスタンスを使用するクラス**NameValueCollection**値を保持します。 2 つのアクセス メソッドを実装、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**名前空間。 **ConfigPropertyBag**クラスは、内部とクラスだけで使用される、 **ConfigParameters**クラスです。  
  
> [!NOTE]
>  プロパティ バッグのキー名は大文字と小文字が区別されません。 基になる**NameValueCollection**ハッシュの大文字と小文字の比較を使用します。  
  
 アプリケーションを使用して、 **ConfigParameters** SSO 構成値を処理するクラス。 このクラスには、次のパブリック メソッドと属性が含まれます。  
  
|メソッドまたは属性|Description|  
|-------------------------|-----------------|  
|SSOConfigParameter|構成パラメータを指定する列挙。|  
|GetConfigParameters|特定のパラメータの値を取得するメソッド。 SSOConfigParameter を使用してパラメータを指定します。|  
  
 **ConfigParameters**クラスは .NET Timer クラスとデリゲート関数の更新設定を使って、 **ConfigPropertyBag**:  
  
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
  
 この静的コンストラクタにより静的メンバの変数が初期化されるので、クラスのインスタンスを作成しなくてもクラス メソッドが使用できるようになります。 コンス トラクターは、SSO 構成ストアのインスタンスを作成する (**ISSOConfigStore**)、構成プロパティ バッグ (**ConfigPropertyBag**)、および同期ロック (**ReaderWriterLock**) へのアクセスを制御するために使用、 **ConfigurationPropertyBag**更新と読み取り中にします。 コンス トラクターを使用し、 **GetConfigInfo** SSO 構成値を取得し、プロパティ バッグに格納します。 最後に、コンス トラクターは、作成、**タイマー** 、一定の間隔の後に、デリゲート関数を呼び出すオブジェクト**cacheRefreshCallback**です。  
  
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
  
 キャッシュ更新コールバック メソッドは、メソッドが最後まで実行されるように、タイマを無効にします。 また、ロックの使用によってプロパティ バッグへのアクセスを制御します。 **ReaderWriterLock**最適な選択肢をここでは、— のケースのものでは書き込みより読み取りができます。 注意しても、ロック**syncLock**が静的では、レベルのすべてのスレッドがその同じ、1 つのインスタンスを共有するクラスで宣言されています。  
  
## <a name="using-sso-from-code"></a>コードからの SSO の使用  
 アダプターの役割に、コードを受け取る必要がありますコードからシングル サインオンを使用する場合。 つまり、メッセージから SSO チケットを取得、バックエンド システムのユーザー名とパスワードを取得するチケットを引き換えると、最後に、バックエンド システムを使用します。 サービス指向ソリューションはこれを**GetPendingTransactionsResponse**のメソッド、 **PendingTransactionsCaller**オブジェクト。  
  
 メソッドの内容は次のとおりです。  
  
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
  
 このメソッドではまず、バックエンド システムの URL やバックエンド (関連) アプリケーションの名前などの構成情報を取得しています。  
  
 チケットを引き換えるために、メソッドはメッセージからチケットと元の要求ユーザー名を抽出する必要があります。 メッセージには、メッセージ コンテキスト プロパティの 1 つとしてチケットが含まれる**BTS です。SSOTicket**です。 詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 メソッドの抽出も、 **OriginatorSID**メッセージ コンテキスト プロパティからです。 メソッドは、抽出したチケットと発信者の名前を使用して、チケットに対して RedeemTicket メソッドを呼び出し、資格情報を取得します。  
  
 残りのコードでは、資格情報の .NET NetworkCredential キャッシュを作成してバックエンド Web サービスを呼び出しています。  
  
> [!NOTE]
>  ユーザー名とパスワードは SSO からクリアテキストで返されるので、その情報が変数に保持されている時間は最小限に抑える必要があります。 コードが内で資格情報の変数を宣言することに注意してください、**再試行**ブロックします。 終了時に変数がここでは、期限切れ、**再試行**ブロックします。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md)