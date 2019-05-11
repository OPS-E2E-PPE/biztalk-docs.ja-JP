---
title: 関連付けの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eea1801632fbeea4eb598f3973923d2436e1d813
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390215"
---
# <a name="correlation-types"></a>関連付けの種類
各関連付けセットがに基づいて、**関連付けの種類**、これは、プロパティの一覧だけです。 これらのプロパティには、データのプロパティは、メッセージ自体内にある、またはシステムまたはメッセージ内で伝えられているデータに関連のないメッセージの詳細を説明するコンテキスト プロパティがあります。  
  
 関連付けの種類は、1 つ以上の関連付けセットで使用できます。 関連付けの種類のプロパティに別の値に関連付ける必要がある場合は、新しい関連付けセットを作成する必要があります: 各関連付けセットを 1 回だけ初期化できます。  
  
 メッセージの特定のプロパティがオーケストレーションにアクセスできることを宣言するプロパティ スキーマのプロパティを昇格することができます。 詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。  
  
> [!CAUTION]
>  システム定義のプロパティを設定しないでください**BTS します。CorrelationToken**各メッセージに関連付けられています。 これは、メッセージを関連付けるときに、エンジンによって使用し、オーケストレーション メッセージの損失になる可能性があります設定するとします。  
  
## <a name="validating-message-correlation-on-send-actions"></a>送信アクションに対するメッセージの関連付けの検証  
 オーケストレーションから送信するメッセージのプロパティを検証する、関連付けセットのプロパティが反映されていることを確認します。 既定では、この検証は無効です。 これを有効にする方法については、次を参照してください。[オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)です。