---
title: エラー - 一括コピー Functoid の子がコードを生成します |Microsoft ドキュメント
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
ms.openlocfilehash: 68183a90be46b176d13100b02cbed2798fe24b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a>エラー - 一括コピー Functoid の子がコードを生成します
**エラー コード**  
  
 btm1068  
  
 **説明**  
  
 機能と矛盾するシナリオ、**一括コピー**マップに functoid が見つかりました。 送信先スキーマの出力にリンクされているノードの子孫のノードで、**一括コピー** functoid は、自身の XSLT コードを生成しようとしています。  
  
 **ユーザーの操作**  
  
 関連の使用法を変更することで、非互換性を削除する**一括コピー** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。