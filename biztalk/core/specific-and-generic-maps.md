---
title: 専用マップと汎用マップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b85658030540ae9b823a5eab32501a200f974c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243210"
---
# <a name="specific-and-generic-maps"></a>専用マップと汎用マップ
データを変換するマップを作成するときに、いずれかを作成、*特定*または*ジェネリック*マップします。  
  
 特定のマップを使用して、特定の取引先パートナーのニーズに対応します。 取引先パートナーと非常に特定のビジネス ニーズやビジネス アグリーメントがある場合は、特定のマップを使用します。 特定のマップの利点は、それを特定の取引先パートナーとビジネス関数のニーズに合わせてカスタマイズしたことです。 特定のマップの欠点は、複数の取引先パートナーと使用できないことです。 取引先と交換するさまざまなメッセージ型の数で取引先パートナーの数を乗算する場合は、十分な時間と関連付けられているマップのすべてを管理するリソースを割り当てる必要があります。  
  
 これに対して、汎用マップは、複数の取引で使用する設計されます。 そのため、開発し、特定のビジネス ドキュメントに対して複数のスキーマの維持を代わりに、ビジネス ドキュメントの種類ごとに 1 つのスキーマを作成して、それらを使用して、すべての取引先パートナーと。 複数の取引先に 1 つのマップを使用するには、時間とリソースが節約できます、これらのマップはカスタマイズされていませんし、すべてのケースのニーズを満たすができない可能性があります。  
  
 ビジネスの性質に応じて、固有および汎用の両方のマップを作成することが可能性があります。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)