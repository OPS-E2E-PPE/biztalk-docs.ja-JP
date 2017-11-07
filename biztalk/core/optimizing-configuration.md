---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 2b0a1aa81971e3e086881e23bcfd6d7ba5d5799d
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="optimize-configuration"></a>構成を最適化します。
このセクションでは、BizTalk Adapter for PeopleSoft Enterprise の構成を最適化する方法について説明します。アダプターをセットアップするためのパラメーターについても説明します。  
  
## <a name="message-overload-protection"></a>メッセージ オーバーロードの保護  
 `Max Concurrent Calls` パラメーターは、構成を最適化することができる機能です。 このパラメータは、スループットがバックエンドの処理機能を上回るインスタンスで使用します。 パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護を有効にする ダイアログ ボックス。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  
  
 BizTalk Server は、送信アダプタに対してメッセージを送信するとき、まず、アダプタからバッチを受け取り、バッチで `TransmitMessage()` を呼び出して各メッセージを転送します。 この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは発行されないことがあります。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。 このパラメータに加えた変更は、すぐに有効になります。 BizTalk Server は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。  
  
## <a name="change-the-max-concurrent-calls-parameter"></a>Max Concurrent Calls パラメーターを変更します。  
  
1.  **送信ポートのトランスポート プロパティ** ダイアログ ボックスで、入力、**接続**値。  
  
     既定値は 40 セッションです。 これより小さい値を使用すると、実行時のパフォーマンスが低下することがあります。 逆の場合も同様に、より大きい値を使用するとサーバーの許容量を超え、実行時エラーが発生することがあります。  
  
2.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
     **エージェントの更新**パラメーターの参照とランタイム エージェントの両方を更新します。 runtimeagent.exe は、1 分間の遅延後または次の send 呼び出し時に更新されます。  
  
3.  PeopleSoft システムにアクセスするための資格情報を設定します。  
  
     システムへのアクセスには、2 つの方法を使用できます。  
  
    -   ログイン資格情報 (Transport Properties Login パラメーター)  
  
    -   シングル サインオン  
  
4.  選択**はい**の**SSO を使用する**でのシングル サインオンを使用します。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[アダプターをセキュリティで保護された](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)です。 
  
5.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。 BizTalk Adapter for PeopleSoft Enterprise は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 取得される資格情報は、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。  
  
    > [!NOTE]
    >  関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。  
  
6.  接続情報を受け入れるように必要なすべての情報を提供すると、をクリックして**適用**、順にクリック**OK**です。  
  
     PeopleSoft にアクセスするには、BizTalk Adapter for PeopleSoft Enterprise に接続パラメーターを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)