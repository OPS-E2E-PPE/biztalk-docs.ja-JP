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
ms.openlocfilehash: 2c18cdcad8deaa9cd76930b91e94860c99749f78
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成する方法
HTTP 受信アダプターを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信できます。 HTTP 受信アダプターは、インターネット インフォメーション サービス (IIS) プロセスでホストされる IIS の ISAPI 拡張です。  
  
### <a name="to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成するには  
  
1.  HTTP 受信アダプター (BTSHTTPReceive.dll) から **\<BizTalk\>\HttpReceive\>** など、シングル サインオン (SSO) プロジェクトが含まれているフォルダーに。  
  
     **< Adapter_install > \biztalk\SSO\mySSODemo**  
  
    1.  新しい Web サービス拡張機能 mySSODemo を追加します。  
  
    2.  見つけてコピー **< BizTalk_install > \HttpReceive** を SSO プロジェクトを次に例を含むフォルダーにします。  
  
         **< Adapter_install > \biztalk\SSO\mySSODemo\BTSHTTPReceive.dll します。**  
  
    3.  MySSODemo Web サービス拡張の状態を設定 **許可**します。  
  
2.  IIS を再起動して、すべての変更内容を適用します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)