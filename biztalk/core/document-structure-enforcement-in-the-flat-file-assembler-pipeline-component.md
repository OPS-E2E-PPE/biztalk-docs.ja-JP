---
title: ドキュメントのフラット ファイル アセンブラー パイプライン コンポーネントにおける構造の強化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], document structure
ms.assetid: 3ac75706-1d4d-443a-a4bf-af8f79a6a092
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028f09b50cf4abd40475163d568e220087fd1f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350942"
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化
フラット ファイル アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照されている場合、参照されたスキーマに対応するメッセージ タイプのドキュメントだけが処理されます。 その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。  
  
> [!NOTE]
>  エンベロープ スキーマは最初のメッセージからのみ取得されます。 エンベロープのプロパティは常に最初のメッセージから取得されます。