---
title: "Web メッセージ部分の型を確認する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e39eb38e919c68405ae18bebde0b46c0b053
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-determine-a-web-message-part-type"></a>Web メッセージ部分の型を判別する方法
特定の Web メッセージの種類の [プロパティ] ウィンドウを使用して、Web メッセージ部分の型がプリミティブ .NET 型かスキーマ型かを判別できます。  
  
### <a name="to-determine-a-web-message-part-type"></a>Web メッセージ部分の型を判別するには  
  
1.  オーケストレーションを開き、[、**ビュー** ] メニューのをクリックして**その他のウィンドウ**、順にクリック**オーケストレーション**です。  
  
2.  展開して、**マルチパート メッセージの種類**ノード、し、Web メッセージの種類を展開します。  
  
3.  メッセージ部分を選択します。  
  
     形式で始まる Web メッセージ部分の署名  **\<*プロジェクトの既定の名前空間*\>.\<*Web 参照名*\>です。参照。\<*スキーマ ルート*\>* * は、スキーマの種類。   **\<*スキーマ ルート*\>* * 型の一部は、Web メッセージ部分を構築する Web 参照スキーマのルート要素です。 それ以外の場合、メッセージ部分の署名はプリミティブ .NET 型などが**System.String**または**System.Int32**です。  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)