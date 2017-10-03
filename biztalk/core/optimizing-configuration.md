---
title: "構成の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Concurrent Calls parameter
- optimizing, configuration
- configuring, optimizing
- messages, overload protection
ms.assetid: df0ae17b-fcfa-4e00-893c-63f4972d3822
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b185d7738ac48d9a1dc3631c7c9faec9ac4b60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-configuration"></a>構成の最適化
このセクションでは、BizTalk Adapter for PeopleSoft Enterprise の構成を最適化する方法について説明します。アダプターをセットアップするためのパラメーターについても説明します。  
  
## <a name="message-overload-protection"></a>メッセージ オーバーロードの保護  
 `Max Concurrent Calls` パラメーターは、構成を最適化することができる機能です。 このパラメータは、スループットがバックエンドの処理機能を上回るインスタンスで使用します。 パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護を有効にする ダイアログ ボックス。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  
  
 BizTalk Server は、送信アダプタに対してメッセージを送信するとき、まず、アダプタからバッチを受け取り、バッチで `TransmitMessage()` を呼び出して各メッセージを転送します。 この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは発行されないことがあります。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。 このパラメータに加えた変更は、すぐに有効になります。 BizTalk Server は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。  
  
#### <a name="to-change-the-max-concurrent-calls-parameter"></a>Max Concurrent Calls パラメーターを変更するには  
  
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
    >  詳細については、次を参照してください。[シングル サインオンを使用して](../core/using-single-sign-on2.md)です。  
  
5.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。 BizTalk Adapter for PeopleSoft Enterprise は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 取得される資格情報は、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。  
  
    > [!NOTE]
    >  関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。  
  
6.  接続情報を受け入れるように必要なすべての情報を提供すると、をクリックして**適用**、順にクリック**OK**です。  
  
     PeopleSoft にアクセスするには、BizTalk Adapter for PeopleSoft Enterprise に接続パラメーターを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)