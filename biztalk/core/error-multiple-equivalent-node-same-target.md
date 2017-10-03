---
title: "エラー - 複数のノードと等しい同じターゲット |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df4f7a68bb1eceaa3211c6aad6e9a581f17a4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-equivalent-node-same-target"></a>エラー - 複数のノードと等しい同じターゲット
**エラー コード**  
  
 btm1025  
  
 **説明**  
  
 競合する子ノードである送信元スキーマのノードの**等価**送信先スキーマのノードにリンクされている両方は、グループ ノード。 任意の 1 つのインスタンス メッセージ内で使用できるのは、送信元スキーマ内のこれらのノードのうち、1 つだけです。  
  
 **ユーザーの操作**  
  
 ノードが 1 つだけの子を確認してください、**等価**グループ ノードが送信先スキーマの特定のノードに接続されています。