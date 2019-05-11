---
title: エラー - マップを移行する必要が |Microsoft Docs
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
ms.openlocfilehash: 0b1b1bee4bcdedecb31dc4b648b505d8ae53b4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389034"
---
# <a name="error---map-needs-to-be-migrated"></a>エラー - マップを移行する必要があります。
**エラー コード**  
  
 btm1064  
  
 **説明**  
  
 以前のバージョンの BizTalk マッパーを使用して作成されたために、マップをコンパイルすることはできません。 コンパイルする前に、このようなマップをこのバージョンの BizTalk マッパーに移行する必要があります。  
  
 **ユーザーの操作**  
  
 現在のバージョンの BizTalk マッパーをマップを移行するには、"xml"から"btm"に関連する Microsoft BizTalk Server プロジェクトに追加するファイル拡張子を変更します。 使用して、**既存項目の追加**コマンドで使用できる、**ファイル**メニューと BizTalk のショートカット メニューの ソリューション エクスプ ローラーでプロジェクトし、ソリューション エクスプ ローラーでダブルクリックしてマップを開きます。 このトピックに達しているため、最初の 2 つの手順を既に実行しました。 現在のバージョンの BizTalk マッパーでマップを開くだけで、マップの場で移行を実行します。