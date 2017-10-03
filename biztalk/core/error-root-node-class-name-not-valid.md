---
title: "エラー - ルート ノードのクラス名が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff170609ef37b1d7f2b00a4d4ca3952b89eef9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---root-node-class-name-not-valid"></a>エラー - ルート ノードのクラス名が有効ではありません。
**エラー コード**  
  
 BEC2012  
  
 **説明**  
  
 **RootNode TypeName**このスキーマのルート ノードのいずれかのプロパティが無効です。 の値、 **RootNode TypeName**プロパティは、自動的に生成された c# クラス名の名前として使用する必要がある必要があります、有効な c# 識別子予約済みの BizTalk キーワードをすることはできません。  
  
 **ユーザーの操作**  
  
 対象のルート ノードを選択してから、Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで変更、 **RootNode TypeName**プロパティ値を正しい c# 識別子は、予約済みの BizTalk キーワードをします。