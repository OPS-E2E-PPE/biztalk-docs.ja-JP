---
title: "ビジネス イベント ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-event-nodes"></a>ビジネス イベント ノード
ビジネス イベント ノードまたはマイルストーン ノードでは、特定の日付または時刻に発生するイベントを定義します。 定義済みのビジネス イベントとマイルストーンのフォルダーは、ビジネス エンド ユーザーからインポートしたアクティビティの定義に含まれています。そのため、これらを削除するには、アクティビティ定義ファイルを再インポートする必要があります。  
  
## <a name="working-with-business-event-nodes"></a>ビジネス イベント ノードの操作  
 図形をオーケストレーションから [Business Events] フォルダーにドラッグして、図形の実行完了時にイベントを追跡することができます。  
  
 TPE では、イベント フォルダー名に図形の名前を使用し、フォルダーには一意のアイコンが使用されます。 たとえば、ローン処理のサンプル シナリオでは、TPE によりイベント フォルダーには [承認済み] や [拒否] などイベントに応じた名前が付けられます。 あるビジネス プロセスが複数の追跡プロファイルにまたがっている場合、ビジネス イベントは 1 つのビジネス プロセスにつき 1 回だけ追跡するようにしてください。 オーケストレーションに条件付きのパスが含まれている場合、イベントは 1 つしか実行されないので、両方のパスからビジネス イベントを選択することができます。 ただし、ループ内の図形は選択しないでください。  
  
> [!NOTE]
>  フォルダーを削除するにはアクティビティ定義を再インポートする必要がありますが、図形 (イベント) はアクティビティ定義を再インポートせずに削除することができます。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)