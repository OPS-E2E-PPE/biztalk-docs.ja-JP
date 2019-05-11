---
title: イベント ソースにマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, alerts
- orchestrations, schedules
- events, mapping sources
- orchestrations, tracking profiles
- events, orchestration schedules
- tracking profiles, orchestrations
- tracking profiles, alerts
- alerts, tracking profiles
- alerts, BAM
- tracking profiles, mapping event sources
- events, tracking profiles
ms.assetid: 507f1624-2cd8-4960-8c63-7797ab22519e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56f9d85d0ac3509eb954f6c2d50496ce5979769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336632"
---
# <a name="how-to-map-event-sources"></a>イベント ソースをマップする方法
BAM は、アラートを生成する追跡データ項目にアクセスするイベント ソースをマップします。  
  
> [!NOTE]
>  4 つの異なるイベント ソースの種類からのデータ項目にマップすることができます。 オーケストレーション スケジュール、メッセージ ペイロード、コンテキスト プロパティ、またはメッセージ プロパティ。 このトピックの手順では、オーケストレーション スケジュールからデータ項目のマッピングについて説明します。  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a>イベント ソースとして、オーケストレーション スケジュールをマップするには  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。  
  
2.  をクリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のウィンドウの上にある) ボタンをクリックします。  
  
3.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
4.  オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**、ボックスの一覧をクリックして**次**します。  
  
     ![TPE 内のイベント ソースとして親アセンブリの選択](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")  
  
5.  内のデータ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**、ボックスの一覧をクリックして**OK**します。  
  
6.  右側のペインで、データ項目を選択し、左側のウィンドウで、アクティビティ内の適切なノードにドラッグします。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)   
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)