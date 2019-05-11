---
title: SOAP アダプターの構成およびチューニング パラメータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 170743f3bd352856fa5c26acabb71f9c9261f2ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314559"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a>SOAP アダプターの構成およびチューニング パラメーター
SOAP アダプターは BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルにエントリを加えることによって、特定の移行先サーバーが表示されますが、同時接続数を構成することができます。  
  
> [!NOTE]
>  このプロパティから同じ HTTP サーバーにメッセージを送信する場合、HTTP および SOAP の両方のアダプターに適用されます。 "Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。  
  
 "最大接続数" プロパティの構成例を次に示します。  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)   
 [HTTP アダプターの構成およびチューニング パラメーター](../core/http-adapter-configuration-and-tuning-parameters.md)