---
title: "SSO Projects1 を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO projects
- running SSO projects
- samples, SSO projects
ms.assetid: f8da1874-7495-47cd-a3a3-881f722c80a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beeeef2a18c32ed0779e5631ac316240e709702e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="running-sso-projects"></a>SSO プロジェクトの実行
このサンプルは、インターネット エクスプローラーから実行できます。  
  
## <a name="running-a-sample-from-internet-explorer"></a>Internet Explorer からサンプルを実行する  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a>Internet Explorer からサンプルを実行するには  
  
1.  ブラウザーを開きます。  
  
2.  次の構文を使用します。  
  
    ```  
    http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
    ```  
  
     例:  
  
     http://localhost/SSODemo/BTSHTTPReceive.dll?<ns0:method_list_method %20xmlns: ns0 ="http://microsoft.com/exposed/object/object1">< ns0:method_list_method >< ns1:method_list %20xmlns: ns1"http://microsoft.com/exposed/ を =オブジェクト">< ns1:comp_code ></ns1:comp_code >< ns1:comp_name ></ns1:comp_name ></ns1:object_1 ></ns0:method_list ></ns0:method_list_method >  
  
     この場合は、資格情報を提供する必要はありません。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)