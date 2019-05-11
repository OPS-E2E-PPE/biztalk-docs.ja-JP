---
title: HTTP 受信 Adapter1 を構成する方法 |Microsoft Docs
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd00bdb0b37de46e04e4568019a4f35318e264ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340884"
---
# <a name="how-to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成する方法
HTTP を使用する受信アダプターにメッセージを送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 HTTP 受信アダプターは IIS プロセスでホストされているインターネット インフォメーション サービス (IIS) の ISAPI 拡張機能。  
  
### <a name="to-configure-the-http-receive-adapter"></a>HTTP 受信アダプターを構成するには  
  
1.  Http 受信アダプター (BTSHTTPReceive.dll) **\<BizTalk\>\HttpReceive\>** シングル サインオン (SSO) プロジェクトを含むフォルダーに。  
  
     **<Adapter_install>\biztalk\SSO\mySSODemo**  
  
    1.  新しい Web サービス拡張機能 mySSODemo を追加します。  
  
    2.  検索してコピー **< BizTalk_install > \HttpReceive**を SSO プロジェクトを含むフォルダーに。  
  
         **<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**  
  
    3.  MySSODemo Web サービス拡張の状態を設定**許可**します。  
  
2.  すべての変更を適用するように IIS を再起動します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)