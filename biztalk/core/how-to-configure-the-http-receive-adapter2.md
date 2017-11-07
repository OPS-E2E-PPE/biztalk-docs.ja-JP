---
title: "HTTP 受信 Adapter2 を構成する方法 |Microsoft ドキュメント"
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
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6e40036308aa872a2d6ba23da8209ee9f80cfc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成する方法
HTTP 受信アダプターを使用すると、メッセージを BizTalk Server に送信できます。 HTTP 受信アダプターは、インターネット インフォメーション サービス (IIS) プロセスでホストされる IIS の ISAPI 拡張です。  
  
### <a name="to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成するには  
  
1.  HTTP 受信アダプター (BTSHTTPReceive.dll) から **\<BizTalk2010 > \HttpReceive >**シングル サインオン (SSO) プロジェクトを含むフォルダーに (たとえば、 **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。  
  
    1.  新しい Web サービス拡張機能 mySSODemo を追加します。  
  
    2.  <BizTalk_install>\HttpReceive に移動し、これを SSO プロジェクト  
  
         (<Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll など) を格納しているフォルダーにコピーします。  
  
    3.  MySSODemo Web サービス拡張機能の状態を設定**許可**です。  
  
2.  IIS を再起動してすべての変更が反映されるようにします。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)