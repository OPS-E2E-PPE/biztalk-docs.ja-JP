---
title: 補正 |Microsoft ドキュメント
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
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231602"
---
# <a name="compensation"></a>[補正]
エラーが発生し、正常にコミットされたトランザクションの効果を元に戻したり、取り消したりする必要がある場合は、オーケストレーションに補正コードを追加します。  
  
 補正は、トランザクションがアクションを正常に完了した後に呼び出すことができます。 この時点で、オーケストレーションの状態は認識されており、状態情報を補正のコードに使用できます。これは、トランザクションがコミットされたときのオーケストレーションの状態に応じて、適切に動作するコードを記述できることを意味します。  
  
 補正は、アトミックのトランザクションでも使用できます。 これらの補正は、アトミックのトランザクションがコミットした後にのみ呼び出すことができます。 補正での通常の実行のパスを元に戻したり、取り消したりするコードを記述する必要があります。  
  
 補正ブロックは柔軟です。別のトランザクション スコープなど、任意の他の図形を格納できます。  
  
> [!NOTE]
>  補正は、指定したスコープで一度だけ実行できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)  
  
-   [カスタム補正をオーケストレーションに追加する方法](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [補正ブロックを追加する方法](../core/how-to-add-a-compensation-block.md)