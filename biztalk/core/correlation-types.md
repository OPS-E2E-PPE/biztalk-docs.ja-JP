---
title: 関連付けの種類 |Microsoft ドキュメント
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
ms.openlocfilehash: b3da5fad8cb4edc1d6a528f481616b4f10efb71d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237778"
---
# <a name="correlation-types"></a>関連付けの種類
各関連付けセットがに基づいて、**関連付けの種類**、これは単にプロパティの一覧です。 これらのプロパティは、メッセージ自体の中に存在するデータ プロパティ、またはメッセージ内で伝えられているデータに関連しないシステムまたはメッセージの詳細を説明するコンテキスト プロパティである可能性があります。  
  
 複数の関連付けセットで、1 つの関連付けの種類を使用できます。 関連付けの種類のプロパティに別の値に関連付ける必要がある場合は、新しい関連付けセットを作成する必要があります: 各関連付けセットを 1 回だけ初期化できます。  
  
 プロパティ スキーマ内のプロパティを昇格して、メッセージ内の特定のプロパティがオーケストレーションからアクセスできることを宣言できます。 詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。  
  
> [!CAUTION]
>  システム定義プロパティを設定しない**BTS です。CorrelationToken**各メッセージに関連付けられています。 これはメッセージの関連付けの際にエンジンによって使用され、これを設定することによって、オーケストレーションのメッセージが失われる結果になる可能性があります。  
  
## <a name="validating-message-correlation-on-send-actions"></a>送信アクションに対するメッセージの関連付けの検証  
 オーケストレーションがその関連付けセット内のプロパティを確実に反映するように、オーケストレーションから送信するメッセージ プロパティを検証できます。 既定では、この検証は無効になっています。 これを有効にする方法については、次を参照してください。 [、オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)です。