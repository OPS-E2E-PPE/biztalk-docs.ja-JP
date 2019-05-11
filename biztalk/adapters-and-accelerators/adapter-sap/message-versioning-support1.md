---
title: メッセージのバージョン管理 Support1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc6a5d1d8bf6d9969deeca33110b1d05d20413ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373210"
---
# <a name="message-versioning-support"></a>メッセージ バージョン管理のサポート
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]操作に対して表示されるメッセージ アクション、名前空間、およびノード Id でバージョン文字列の要素を含めることでバージョン管理をサポートしています。 現在のバージョンは http://Microsoft.LobServices.Sap/2007/03します。 つまりの"RFC_SAMPLE"という名前 RFC、アダプター、RFC 操作は、次の。  
  
-   ノードの ID。 http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   メッセージのアクション: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc  
  
> [!NOTE]
>  この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)