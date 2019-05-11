---
title: 補正 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba08eecad12c08a3bebd6f4704d7df82b74d279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357887"
---
# <a name="compensation"></a>補正
エラーが発生した、元に戻すか、正常にコミットされたトランザクションの効果を反転する必要がある場合は、オーケストレーションに補正コードを追加することでこれを実行できます。  
  
 トランザクションがそのアクションを正常に完了した後は、補正を呼び出すことができます。 その時点では、オーケストレーションの状態がわかっている場合と、状態情報は、補正は、トランザクションのコミット時に、オーケストレーションの状態に応じて適切に動作するコードを記述することを意味のコードに提供します。  
  
 補正は、アトミックのトランザクションも指定できます。 これらの補正は、アトミックのトランザクションがコミットされた後にのみ呼び出すことができます。 元に戻す補正では、通常の実行のパスに戻したりするコードを記述する必要があります。  
  
 補正ブロックでは柔軟性があります。別のトランザクション スコープを含むその他の図形を含めることができます。  
  
> [!NOTE]
>  指定されたスコープの補正を 1 回だけ行うことができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)  
  
-   [カスタム補正をオーケストレーションに追加する方法](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [補正ブロックを追加する方法](../core/how-to-add-a-compensation-block.md)