---
title: 省略可能なノード |Microsoft ドキュメント
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
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263346"
---
# <a name="optional-nodes"></a>省略可能なノード
省略可能なノードを使用すると、マップをテストしたときに警告が生成されます。 送信元ノードが省略可能であると見なされる条件には、次の 2 つがあります。  
  
-   実際のレコードまたはフィールドが省略可能である。  
  
-   送信元のレコードまたはフィールドは必須であるが、親、先祖、それより上位の階層が省略可能である。  
  
 たとえば、送信元スキーマに省略可能なレコードやフィールドがあり、送信先スキーマに対応するレコードまたはフィールドが必要な場合などが考えられます。  
  
 可能な条件の両方で、マップのテストで警告を生成、**出力**ウィンドウです。 また、出力データは対象ノードには取り込まれません。  
  
## <a name="see-also"></a>参照  
 [マップのテスト](../core/testing-maps.md)