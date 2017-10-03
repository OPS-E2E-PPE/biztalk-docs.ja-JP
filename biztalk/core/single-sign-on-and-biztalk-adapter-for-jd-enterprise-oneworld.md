---
title: "シングル サインオンと BizTalk Adapter JD Enterprise OneWorld for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9d3d102c3ab79ea719587fdb3632612e75faa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a>シングル サインオンと BizTalk Adapter for JD Enterprise OneWorld
シングル サインオン (SSO) 資格情報がデータベースから取得した、SSO 資格情報です。したがって、する必要はありませんでサーバー システムのログオン資格情報を入力する、**トランスポートのプロパティ**ウィンドウです。  
  
 デザイン時には、Microsoft BizTalk Adapter for JD Edwards OneWorld が、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。 このユーザーは、アプリケーション ユーザーである必要があります。  
  
 実行時には、SSO を使用するときにパススルーのシナリオで受信場所として BizTalk Adapter for JD Edwards OneWorld を使用してください。  
  
 インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。 このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。  
  
 次に、メッセージがメッセージ ボックス データベースに転送されます。 アダプタは、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して IBTSTicket.ValidateAndRedeemTicket メソッドを呼び出し、ログオン資格情報を SSO ストアから取得します。 その後、BizTalk Adapter for JD Edwards OneWorld は外部の資格情報を使用してシステムに接続し、要求を処理します。  
  
> [!NOTE]
>  SSO の構成は BizTalk Server のセットアップの一部として行います。 SSO エラーが発生した場合は、あるアカウントを使用したドメイン BizTalk Server を構成したときに、エンタープライズ SSO サービスの機能に影響するためことを確認します。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications3.md)   
 [シングル サインオンを使用します。](../core/using-single-sign-on3.md)