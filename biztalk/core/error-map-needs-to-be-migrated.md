---
title: エラー - マップを移行する必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---map-needs-to-be-migrated"></a>エラー - マップを移行する必要があります。
**エラー コード**  
  
 btm1064  
  
 **説明**  
  
 マップは、以前のバージョンの BizTalk マッパーを使用して作成されているため、コンパイルできません。 このようなマップをコンパイルするには、現在のバージョンの BizTalk マッパーに移行する必要があります。  
  
 **ユーザーの操作**  
  
 このマップを現在のバージョンの BizTalk マッパーに移行します。これには、マップのファイル拡張子を "xml" から "btm" に変更し、ファイルを適切な Microsoft BizTalk Server プロジェクトに追加します。 使用して、**既存項目の追加**コマンドで使用できる、**ファイル**メニューと BizTalk のショートカット メニューの ソリューション エクスプローラで、プロジェクトおよびソリューション エクスプ ローラーでダブルクリックして、マップを開きます。 ヘルプの各トピックを順番に参照している場合は、最初の 2 つの手順は既に完了しています。 現在のバージョンの BizTalk マッパーでマップを開くだけで、非常に簡単にマップを移行できます。