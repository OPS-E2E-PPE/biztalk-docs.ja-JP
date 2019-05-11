---
title: エラー - 一括コピー Functoid の子がコードを生成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11f96b753b100a9662671ff0c20d5671ad07055
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349005"
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a>エラー - 一括コピー Functoid の子がコードを生成します。
**エラー コード**  
  
 btm1068  
  
 **説明**  
  
 機能と矛盾するシナリオ、**一括コピー**マップに functoid が見つかりました。 送信先スキーマの出力にリンクされているノードの子孫のノードで、**一括コピー** functoid は自身の XSLT コードを生成しようとしています。  
  
 **ユーザーの操作**  
  
 非互換性を関連する使用状況を変更することで削除**一括コピー** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。