---
title: Web メッセージ部分の型を確認する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb191f72612d364d69600f0d6e22505b6196b056
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338614"
---
# <a name="how-to-determine-a-web-message-part-type"></a>Web メッセージ部分の型を確認する方法
Web メッセージ部分の型が指定した Web メッセージの種類のプロパティ ウィンドウを使用して、プリミティブ .NET 型またはスキーマ型がある場合を判断できます。  
  
### <a name="to-determine-a-web-message-part-type"></a>Web メッセージ部分の型を決定するには  
  
1.  オーケストレーションを開いて、**ビュー**  メニューのをクリックして**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  展開、**マルチパート メッセージの種類**ノード、し、Web メッセージの種類を展開します。  
  
3.  メッセージ部分を選択します。  
  
     形式で始まる Web メッセージ部分の署名 **\<*プロジェクトの既定の名前空間*\>.\<*Web 参照名*\>します。参照。\<*スキーマ ルート*\>** はスキーマの一種です。 **\<*スキーマ ルート*\>** 型の一部は、Web メッセージ部分を構築する Web 参照スキーマのルート要素。 それ以外の場合、プリミティブ .NET 型は、メッセージ部分の署名など**System.String**または**System.Int32**します。  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)