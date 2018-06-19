---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 1a32564f9e0e9e81624b39ab0ba156e76b109497
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014041"
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a>TIBCO Enterprise Message Service 受信ポートのトランスポート プロパティの設定
TIBCO Enterprise Message System (EMS) の受信場所を**URL**と**Target Namespace** TIBCO EMS システムには、必要な唯一の構成値。  
  
### <a name="to-specify-tibco-ems-transport-properties"></a>TIBCO EMS トランスポートのプロパティを指定するには  
  
1.  展開して、**システム定義**し、TIBCO EMS サーバーに接続に必要なすべての情報を入力します。  
  
2.  展開**メッセージの処理**し必要なすべての情報を入力します。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**メッセージ セレクター**|メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。<br /><br /> 受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。<br /><br /> メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。 構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。<br /><br /> たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。|  
    |**再試行の回数**|トランスポートの再試行の回数です。 既定値は 0 です。|  
    |**再試行の間隔**|アダプターが再試行を開始するまでに待機する時間です。 既定値は、5 分です。|  
  
3.  展開して、**サーバー接続の定義**し必要なすべての情報を入力します。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**変換先**|必須の設定です。 送信先の名前と種類を定義します。 キューまたはトピックを Queue[queue.name] または Topic[topic.name] という形式で定義します。|  
    |**[ポート番号]**|TIBCO EMS サーバーがリッスンするポートです。|  
    |**[サーバー名]**|必須の設定です。 TIBCO EMS サーバーをホストしているシステムの名前です。|  
  
4.  シングル サインオン (SSO) を使用する資格情報を指定します。  
  
     TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。 資格情報 (ユーザー名とパスワードのパラメーター) を使用するまたはシングル サインオンします。  
  
    -   選択**はい**で**SSO を使用する**でのシングル サインオンを使用します。  
  
    -   一覧で関連アプリケーションを選択します。  
  
         エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。 Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。  
  
         関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。  
  
5.  展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |`Password`|TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。<br /><br /> 選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
    |`User Name`|TIBCO EMS デーモンとの通信に使用するユーザーの名前です。<br /><br /> 選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
  
6.  をクリックして**適用**、順にクリック**OK**です。  
  
## <a name="see-also"></a>参照  
  [TIBCO Enterprise Message Service 受信ハンドラーの作成](../core/creating-tibco-enterprise-message-service-receive-handlers.md)