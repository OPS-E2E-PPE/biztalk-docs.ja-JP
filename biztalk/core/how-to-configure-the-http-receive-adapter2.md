---
title: HTTP 受信 Adapter2 を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73b04356f7c09d8aa2a24d816f02dc66e5d414d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340840"
---
# <a name="how-to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成する方法
HTTP を使用する受信アダプターは BizTalk Server にメッセージを送信します。 HTTP 受信アダプターは IIS プロセスでホストされているインターネット インフォメーション サービス (IIS) の ISAPI 拡張機能。  
  
### <a name="to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成するには  
  
1.  Http 受信アダプター (BTSHTTPReceive.dll)  **\<BizTalk2010 > \HttpReceive >** シングル サインオン (SSO) プロジェクトが含まれるフォルダーに (たとえば、 **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。  
  
    1.  新しい Web サービス拡張機能 mySSODemo を追加します。  
  
    2.  参照して、たとえば、SSO プロジェクトが含まれるフォルダーにコピー < BizTalk_install > \HttpReceive  
  
         <Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.  
  
    3.  MySSODemo Web サービス拡張の状態を設定**許可**します。  
  
2.  すべての変更が有効なことを確認するには、次のように IIS を再起動します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)