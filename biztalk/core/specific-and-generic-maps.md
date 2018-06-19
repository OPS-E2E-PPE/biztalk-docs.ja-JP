---
title: 専用マップと汎用マップ |Microsoft ドキュメント
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
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276306"
---
# <a name="specific-and-generic-maps"></a>専用マップと汎用マップ
データを変換するマップを作成するときは、いずれかを作成、*特定*または*ジェネリック*マップします。  
  
 専用マップを使用すると、特定の取引先の要件を満たすことができます。 取引先との間に非常に特殊なビジネスの要件 (または契約) がある場合には、専用マップを使用します。 専用マップの利点は、カスタマイズして、特定の取引先とのビジネス関数の要件を満たせることです。 専用マップの欠点は、複数の取引先に使用できないことです。 取引先の数と、取引先と交換されるさまざまなメッセージの種類の数とを乗算した数のマップが必要である場合、関連するすべてのマップを管理するために、十分な時間とリソースを割り当てる必要があります。  
  
 一方、汎用マップは、複数の取引先に使用するために設計されています。 このため、特定のビジネス ドキュメントに対して複数のスキーマの開発や管理を行う代わりに、ビジネス ドキュメントの種類ごとに 1 つのスキーマを作成し、作成したスキーマをすべての取引先に対して使用します。 複数の取引先に対して 1 つのマップを使用すると、時間とリソースが節約されます。ただし、このようなマップは、カスタマイズできないので、すべてのケースのニーズを満たせない場合があります。  
  
 業務の種類にもよりますが、専用マップと汎用マップの両方を作成する場合がほとんどです。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)