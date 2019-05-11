---
title: 省略可能なノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbab14a66f0ac88f32e945bf7b9c738eb419b654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323402"
---
# <a name="optional-nodes"></a>省略可能なノード
省略可能なノードを使用して、マップをテストするときに警告が生成されます。 省略可能な見なすことがソース ノードを 2 つの条件があります。  
  
- 実際のレコードまたはフィールドは省略可能です。  
  
- ソースのレコードまたはフィールドが必要ですが、親、親の親、およびそれより上位の階層は省略可能です。  
  
  場合は、レコードと省略可能な送信元スキーマ内のフィールドがあるときにする必要がありますが、送信先スキーマは、対応するレコードまたはフィールドが必要です。  
  
  可能な条件の両方で、マップのテストで警告を生成、**出力**ウィンドウ。 さらに、出力データは、ターゲット ノードは含まれません。  
  
## <a name="see-also"></a>参照  
 [マップのテスト](../core/testing-maps.md)