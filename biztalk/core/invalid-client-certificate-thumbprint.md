---
title: "無効なクライアント証明書の拇印 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84401d28261b13c6f49a063f34e29054a4aba108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-client-certificate-thumbprint"></a>クライアント証明書の拇印が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|クライアント証明書の拇印が無効です。40 桁の 16 進数が必要です。|  
  
## <a name="explanation"></a>説明  
 無効なクライアント証明書の拇印が指定されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF 送信ポートを構成するコードで、ユーザー インターフェイスのクライアント証明書プロパティには、16 進の 40 桁の値を指定します。 例: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 証明書の詳細については、次を参照してください。  
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)