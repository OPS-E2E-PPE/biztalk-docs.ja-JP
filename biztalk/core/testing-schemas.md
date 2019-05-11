---
title: スキーマのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8331026992e9715793cf366409cb68904e5058c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298969"
---
# <a name="testing-schemas"></a>スキーマのテスト
スキーマを作成すると、意図を記述する XML 構造が説明されているかを検証したい場合があります。 検証するのには、スキーマに次の 3 つの操作を実行できます。  
  
- **インスタンス生成**します。 この操作は、XML 要素と、スキーマで指定された属性に付随するテスト データの作成、スキーマからインスタンス メッセージを生成します。  
  
- **スキーマ検証**です。 この操作は、XML スキーマ定義 (XSD) 言語スキーマの標準に準拠しているスキーマの内部の一貫性を検証します。  
  
- **インスタンスの検証**です。 この操作は、スキーマに対する特定のインスタンス メッセージを検証します。  
  
  これらの操作の 3 つすべては運用環境で使用して配置する前に、スキーマのテストに役立ちます。  
  
  このセクションでは、これらの操作をさらに詳しく説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Visual Studio でのスキーマを検証する方法](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [インスタンス メッセージを検証する方法](../core/how-to-validate-instance-messages.md)  
  
-   [インスタンス メッセージを生成する方法](../core/how-to-generate-instance-messages.md)