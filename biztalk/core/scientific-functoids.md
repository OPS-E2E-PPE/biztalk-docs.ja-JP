---
title: 関数 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6255b6e7d4cc81eea493c1f9d81211c27771d371
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395550"
---
# <a name="scientific-functoids"></a>関数 Functoid

## <a name="overview"></a>概要
**科学**functoid は、さまざまな標準の三角関数演算、対数演算、および指数演算を実行するために使用します。  

 例外として、**底指定対数**と**X ^ Y** functoid をそれぞれ 2 つの入力パラメーターを取る、**科学的**すべての functoid が 1 つのパラメーターを受け取る。  

 4 つの三角関数**科学的**functoid (**アーク タンジェント**、**コサイン**、**サイン**、および**タンジェント**)、関連する入力または出力パラメーターの単位として度ではなく、ラジアンを使用すべて。 ラジアンは、2 π ラジアンを円でが存在するよう、角度の単位の単位です。 これを次に示します。  

- 2π radians equals 360 degrees  

- 1 radian = 180/π degrees  

- 1 度 = π/180 ラジアン  

  入力または出力インスタンス メッセージには、角度のメジャーの単位として度を使用して、使用する必要があります、**数値演算**functoid は三角関数と組み合わせて**科学的**functoid を正しい結果を実現します。  

## <a name="available-functoids"></a>使用可能な functoid  
 **科学的**functoid には。 

* 10 ^ n
* アーク タンジェント
* 底指定対数
* 常用対数
* コサイン
* 自然指数関数
* 自然対数
* サイン
* タンジェント
* X ^ Y

## <a name="see-also"></a>参照  
- [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
- **関数 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
