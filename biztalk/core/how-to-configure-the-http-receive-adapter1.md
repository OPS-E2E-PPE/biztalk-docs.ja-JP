---
title: "HTTP 受信 Adapter1 を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6907a96c3c961a4df7d076ba9307f44627bfa2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成する方法
HTTP 受信アダプターを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信できます。 HTTP 受信アダプターは、インターネット インフォメーション サービス (IIS) プロセスでホストされる IIS の ISAPI 拡張です。  
  
### <a name="to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成するには  
  
1.  HTTP 受信アダプター (BTSHTTPReceive.dll) から **\<BizTalk > \HttpReceive >**など、シングル サインオン (SSO) プロジェクトが含まれているフォルダーに。  
  
     **< Adapter_install > \biztalk\SSO\mySSODemo**  
  
    1.  新しい Web サービス拡張機能 mySSODemo を追加します。  
  
    2.  コピーを見つけて**< BizTalk_install > \HttpReceive**など、SSO プロジェクトが含まれているフォルダーに。  
  
         **< Adapter_install > \biztalk\SSO\mySSODemo\BTSHTTPReceive.dll です。**  
  
    3.  MySSODemo Web サービス拡張機能の状態に設定**許可**です。  
  
2.  IIS を再起動して、すべての変更内容を適用します。  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on2.md)