---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f4b67492efd40f8759c3cc2c490e4427b0272fb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383862"
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a>TIBCO Rendezvous トランスポートのプロパティを設定する方法
TIBCO Rendezvous トランスポートのプロパティは、実行時に使用されます。 **トランスポートのプロパティ** 画面で、生成されたメッセージを公開する TIBCO Rendezvous ドメインを識別する接続パラメーターを設定します。  
  
## <a name="enter-tibco-rendezvous-transport-properties"></a>TIBCO Rendezvous トランスポートのプロパティを入力します。  
  
1.  **TIBCO Rendezvous トランスポートのプロパティ**画面で、展開**証明された送信者プロパティ**し、次の情報を入力します。  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**元帳の名前**|既定値は空白です。 永続的な認証されたメッセージ配信に使用する台帳ファイル名。 ローカル ドライブのみを使用します。|  
    |**再利用可能な名前**|既定値は空白です。 認証されたメッセージ配信に使用する再利用可能な送信者名です。 この名前は、ネットワーク上のすべての認証されたメッセージの送信者名の中で一意である必要があります。|  
  
2.  展開**資格情報**しサーバーへの接続に関する次の情報を入力します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Password**|既定値は空白です。 Tibco Rendezvous デーモンにログインするためのパスワードです。|  
    |**ユーザー名**|既定値は空白です。 Tibco Rendezvous デーモンで使用するユーザー名です。|  
  
3.  展開**全般設定**し、TIBCO Rendezvous サーバーへの接続に関する次の情報を入力します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コード ページ番号**|既定値は 65001 (UTF-8 エンコーディングのコード ページ) です。 これは、TIBCO Rendezvous SDK が文字列のエンコーディングに使用するコード ページです。|  
    |**既定のサブジェクト名**|既定では空になっています。 サブジェクト名はオーケストレーションで設定されます。 1 つの種類のメッセージに 1 つのポートを使用する場合、既定のサブジェクト名を指定でき、サブジェクト名プロパティを設定する必要をなくしてオーケストレーションを単純化できます。|  
    |**タイム バッチを有効にします。**|既定値は False です。 TIBCO Rendezvous のタイム バッチ機能を有効または無効にします。|  
    |**サポートされていない型を文字列にマップします。**|既定値は True です。 True の場合、サポートされていない型はすべて文字列型にマップされます。 False の場合、実行時エラーが生成されます。|  
    |**TIBCO Rendezvous アセンブリなどのバイナリのパス**|PATH 環境変数でまだ設定されていない場合は、この情報を指定します。|  
    |**順序の保持**|既定値は True です。 ロジックで、メッセージを BizTalk Server から受信したときと同じ順序で TIBCO Rendezvous に送信できます。 このパラメーターにより、同じ順序での公開が強制されますが、サブスクライバーが同じ順序で受信するということではありません。|  
    |**送信ポートの識別子**|この識別子は、このポートに関連付けられているログ メッセージに表示されます。 これは、便宜上指定します。|  
  
4.  展開**Rendezvous トランスポート**TIBCO Rendezvous サーバーに接続の情報を入力し、**適用**、順にクリックします**OK**します。  
  
     Microsoft BizTalk Adapter for TIBCO Rendezvous が TIBCO Rendezvous にアクセスできるようにするために接続パラメーターを設定する必要があります。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**デーモン**|既定では空になっています。<br /><br /> Rendezvous トランスポート デーモン パラメーター。|  
    |**Network**|既定では空になっています。<br /><br /> Rendezvous トランスポート ネットワーク パラメーター。|  
    |**サービス**|既定では空になっています。<br /><br /> Rendezvous トランスポート サービス パラメーター。|  
  
5.  シングル サインオン (SSO) を使用する資格情報を指定します。  
  
     TIBCO Rendezvous システムにアクセスする方法は 2 つあります。 1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。  
  
    1.  選択**はい**で、**を使用して SSO**でシングル サインオンを使用します。  
  
        > [!NOTE]
        >  参照してください[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)SSO を設定する方法についてはします。  
  
    2.  一覧から関連アプリケーションを選択します。  
  
         エンタープライズ シングル サインオン ツールで作成された関連アプリケーションは TIBCO Rendezvous などのアプリケーションを表します。 Microsoft BizTalk Adapter for TIBCO Rendezvous では、アプリケーション ユーザーの資格情報が使用されます。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。  
  
        > [!NOTE]
        >  関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications1.md)します。  
  
6.  クリックして**適用**、順にクリックします**OK**接続情報を受け入れるように必要なすべての情報を入力したら。  
  
     BizTalk Adapter for TIBCO Rendezvous にアクセスする TIBCO Rendezvous の接続パラメーターを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)