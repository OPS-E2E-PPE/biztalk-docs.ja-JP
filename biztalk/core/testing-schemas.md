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
ms.openlocfilehash: fc036be84bb64e794e6109e1ebc4ec730f382878
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023112"
---
# <a name="testing-schemas"></a>スキーマのテスト
スキーマを作成した後、XML 構造が正しいかどうかを検証したい場合があります。 スキーマに対して次の 3 つの操作を実行して、検証を行うことができます。  
  
- **インスタンス生成**します。 この結果、スキーマで指定された XML 要素および XML 属性と共にテスト データが作成されます。  
  
- **スキーマ検証**です。 標準の XSD (XML Schema Definition) 言語のスキーマに準拠しているかどうかが検証されます。  
  
- **インスタンスの検証**です。 この操作は、スキーマに対する特定のインスタンス メッセージを検証します。  
  
  これらの 3 つの操作は、実稼働環境で運用する前にスキーマをテストする場合に便利です。  
  
  このセクションでは、これらの操作の詳細について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Visual Studio でのスキーマを検証する方法](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [インスタンス メッセージを検証する方法](../core/how-to-validate-instance-messages.md)  
  
-   [インスタンス メッセージを生成する方法](../core/how-to-generate-instance-messages.md)