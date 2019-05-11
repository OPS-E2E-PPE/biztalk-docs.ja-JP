---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7d7c30262fabbbde4f555deb7f0b01c3ef4ffb95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262989"
---
# <a name="optimize-configuration"></a>構成を最適化します。
このセクションでは、BizTalk adapter for PeopleSoft Enterprise 構成を最適化する方法について説明し、アダプターを設定するためのパラメーターの説明が含まれています。  
  
## <a name="message-overload-protection"></a>メッセージ オーバー ロードの保護  
 `Max Concurrent Calls`パラメーターは、機能、構成を最適化することができます。 スループットがバックエンド処理機能を上回るインスタンスでは、このパラメーターを使用します。 パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護をアクティブにする ダイアログ ボックス。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  
  
 BizTalk Server では、送信アダプターにメッセージを送信するときに最初にアダプターからバッチを受信し、呼び出します`TransmitMessage()`で各メッセージを送信するバッチ。 この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server は、前に複数のバッチを取得した場合`Done`が呼び出される、`Done`コマンドが発生することはありません。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。 このパラメーターを変更するには、1 分で有効です。 BizTalk Server では、SQL database に保存されているアダプター構成に対する変更を取得する必要があります。  
  
## <a name="change-the-max-concurrent-calls-parameter"></a>Max Concurrent Calls パラメーターを変更します。  
  
1.  **送信ポートのトランスポート プロパティ** ダイアログ ボックスに、入力、**接続**値。  
  
     既定値は、40 セッションです。 小さい値を使用する場合は、実行時のパフォーマンスの低下があります。 逆の場合も同様です。大きい値には、実行時エラーの結果、サーバーの機能を超える可能性があります。  
  
2.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
     **エージェントの更新**両方参照エージェントとランタイム エージェント パラメーターを更新します。 または次の 1 つ分の遅延の後、runtimeagent.exe 更新プログラムは、呼び出しを送信します。  
  
3.  PeopleSoft システムにアクセスする資格情報を提供します。  
  
     2 つのメソッドを使用するには、システムにアクセスします。  
  
    -   ログイン資格情報 (Transport Properties Login パラメーター)  
  
    -   シングル サインオン  
  
4.  選択**はい**の**を使用して SSO**でシングル サインオンを使用します。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)します。 
  
5.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 資格情報では、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) のものです。  
  
    > [!NOTE]
    >  関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。  
  
6.  接続情報を受け入れるように必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします**OK**します。  
  
     BizTalk Adapter for PeopleSoft Enterprise PeopleSoft へのアクセスの接続パラメーターを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)