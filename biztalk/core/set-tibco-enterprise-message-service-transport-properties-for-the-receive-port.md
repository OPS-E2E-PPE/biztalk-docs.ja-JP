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
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a>TIBCO Enterprise Message Service 受信ポートのトランスポート プロパティの設定
TIBCO Enterprise Message System (EMS) の受信場所、 **URL**と**Target Namespace** TIBCO EMS システムには必要な唯一の構成値。  
  
### <a name="to-specify-tibco-ems-transport-properties"></a>TIBCO EMS トランスポートのプロパティを指定するには  
  
1.  展開、**システム定義**し、TIBCO EMS サーバーへの接続に必要なすべての情報を入力します。  
  
2.  展開**メッセージの処理**必要なすべての情報を入力します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |**メッセージ セレクター**|メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。<br /><br /> 受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。<br /><br /> メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。 構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。<br /><br /> たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。|  
    |**再試行の回数**|トランスポートの再試行の回数です。 既定値は 0 です。|  
    |**再試行の間隔**|アダプターが再試行を開始するまでに待機する時間です。 既定値は、5 分です。|  
  
3.  展開、**サーバー接続の定義**必要なすべての情報を入力します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |**変換先**|必須の設定です。 送信先の名前と種類を定義します。 次の形式でキューまたはトピックを定義します。Queue[queue.name] または Topic[topic.name]。|  
    |**[ポート番号]**|TIBCO EMS サーバーがリッスンするポートです。|  
    |**[サーバー名]**|必須の設定です。 TIBCO EMS サーバーをホストしているシステムの名前です。|  
  
4.  シングル サインオン (SSO) を使用する資格情報を指定します。  
  
     TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。 資格情報 (ユーザー名とパスワードのパラメーター) を使用するか、シングル サインオンします。  
  
    -   選択**はい**で**を使用して SSO**でシングル サインオンを使用します。  
  
    -   一覧で関連アプリケーションを選択します。  
  
         エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。 Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。  
  
         関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。  
  
5.  展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Password`|TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。<br /><br /> 選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
    |`User Name`|TIBCO EMS デーモンとの通信に使用するユーザーの名前です。<br /><br /> 選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
  
6.  クリックして**適用**、順にクリックします**OK**します。  
  
## <a name="see-also"></a>参照  
  [TIBCO Enterprise Message Service 受信ハンドラーの作成](../core/creating-tibco-enterprise-message-service-receive-handlers.md)