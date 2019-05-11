---
title: 無効なクライアント証明書の拇印 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f349dbc2eb3ffd6a1bfa38c3231461d45a8ae7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381386"
---
# <a name="invalid-client-certificate-thumbprint"></a>クライアント証明書の拇印が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |       無効なクライアント証明書の拇印。40 桁の 16 進数が必要です。       |
  
## <a name="explanation"></a>説明  
 無効なクライアント証明書の拇印が指定されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF 送信ポートを構成するコードでは、ユーザー インターフェイスのクライアント証明書のプロパティには 40 桁の 16 進数の値が期待しています。 例:798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 証明書の詳細については、次を参照してください。  
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)