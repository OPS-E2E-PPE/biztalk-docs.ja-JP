---
title: SOAP アダプターの構成およびチューニング パラメータ |Microsoft ドキュメント
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
ms.openlocfilehash: be6a71938876ad932a58d369abe40d7c8b073f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277346"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a>SOAP アダプタの構成およびチューニング パラメータ
BizTalk Server をインストールしたルート ディレクトリに存在する BTSNTSvc.exe.config ファイルにエントリを作成することで、SOAP アダプタから特定の接続先サーバーへの同時接続の数を構成できます。  
  
> [!NOTE]
>  このプロパティは、HTTP アダプタと SOAP アダプタから同じ HTTP サーバーにメッセージを送信する場合に、両方のアダプタに適用されます。 "Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。  
  
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
 [HTTP アダプタの構成およびチューニング パラメータ](../core/http-adapter-configuration-and-tuning-parameters.md)