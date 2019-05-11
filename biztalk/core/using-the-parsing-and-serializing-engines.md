---
title: 解析を使用して、エンジンをシリアル化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78e0dcffd680136cd2a140f18787793b43a4913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302983"
---
# <a name="using-the-parsing-and-serializing-engines"></a>解析およびシリアル化エンジンを使用します。
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解析とシリアル化の解析とフラット ファイル ドキュメントをシリアル化プロセスを簡易化エンジンが含まれています。  
  
 解析エンジンは、スキーマ主導のフレームワークで、多くのさまざまなドキュメント形式を XML に解析できます。 また、エンジンより簡単にカスタム形式の解析を明確に定義された機能拡張モデル。  
  
 複雑な解析、逆アセンブラーが使用されます。 ネイティブ形式を XML に変換するだけでなく、逆アセンブラーは 1 つのドキュメントを複数のドキュメントに分割することができますも。  
  
 シリアル化エンジンは、反対方向に正常に機能する点を除いて、解析エンジンと似ています。 解析エンジンでは、ネイティブ形式を XML に変換して、場所、シリアル化エンジンは、XML をネイティブ形式に変換します。 解析エンジンは、逆アセンブラーを使用すると同様、シリアル化エンジンはアセンブラーを使用します。  
  
 文字エン コードの実行、解析し、シリアル化する方法を説明する XML スキーマ定義言語 (XSD) スキーマに基づいており、解析エンジンおよびシリアル化エンジン Api を使用して他の一般的なタスクを実行します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン コンポーネントでの文字エンコードの実装](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [スキーマの使用](../core/using-schemas.md)  
  
-   [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)  
  
-   [フラット ファイル シリアル化エンジンの使用](../core/using-the-flat-file-serializing-engine.md)