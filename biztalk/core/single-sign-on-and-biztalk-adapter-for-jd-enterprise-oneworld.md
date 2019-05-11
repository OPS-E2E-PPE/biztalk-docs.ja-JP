---
title: シングル サインオンと BizTalk Adapter JD Enterprise OneWorld 単一 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec5be842305bbad1fb6e6963b4fcdd770a989224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393040"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a>単一でサインオンと BizTalk Adapter JD Enterprise OneWorld
シングル サインオン (SSO) 資格情報は、SSO 資格情報データベースから取得されます。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**ウィンドウ。  
  
 デザイン時に、Microsoft BizTalk Adapter for JD Edwards OneWorld は、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。 そのユーザーは、アプリケーション ユーザーである必要があります。  
  
 実行時にを使用して、BizTalk Adapter for JD Edwards OneWorld パススルーのシナリオで受信場所としての SSO を使用する場合。  
  
 インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。 このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。  
  
 メッセージは、メッセージ ボックス データベースに送られます。 アダプターはメッセージを受信、メッセージ ボックス データベースから、ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に、暗号化されたチケットを指定して IBTSTicket.ValidateAndRedeemTicket メソッドを呼び出します。 BizTalk Adapter for JD Edwards OneWorld には、外部の資格情報がシステムに接続し、要求を処理します。  
  
> [!NOTE]
>  SSO の構成は、BizTalk Server のセットアップの一部です。 SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、エンタープライズ SSO サービスの機能に影響するためことを確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications3.md)   
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)