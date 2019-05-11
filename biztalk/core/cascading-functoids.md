---
title: カスケード Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Cascading
- Cascading functoids
ms.assetid: 03c46e7b-be1c-475e-b68b-f9d1d7732fce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020ff5eeb4bed7e5f1c6a09b1757300f2db525e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357607"
---
# <a name="cascading-functoids"></a>カスケード Functoid
送信先スキーマのレコードまたはフィールドにリンクする前に、ある Functoid が別の Functoid にリンクしている場合、Functoid が連鎖しているといいます。 たとえば、2 つの文字列を連結して別の文字列を生成し、送信先スキーマのフィールドに入力する場合に、Functoid の連鎖を作成します。  
  
 Functoid を連鎖させる場合、グリッド ページに複数の連続する変換を作成できます。 1 ページ内で連鎖する Functoid の数に制限はありませんが、連鎖は効率的に使用してください。 複雑な連鎖を使用すると、入力インスタンス メッセージから出力インスタンス メッセージへの変換にかかる時間が長くなり、実行時のパフォーマンスが大幅に低下する可能性があります。  
  
## <a name="see-also"></a>参照  
 [マップの Functoid](../core/functoids-in-maps.md)   
 [Functoid を使用した複雑なマッピングの作成](../core/using-functoids-to-create-more-complex-mappings.md)