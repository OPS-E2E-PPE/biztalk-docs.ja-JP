---
title: イベント ソースにマップする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 588a394fb3404872554fc786efa3fe24fdd9b47a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253890"
---
# <a name="how-to-map-event-sources"></a>イベント ソースをマップする方法
イベント ソースをマップすると、BAM による追跡と警告の対象となるデータ項目へのアクセスが可能になります。  
  
> [!NOTE]
>  データ項目は、オーケストレーション スケジュール、メッセージ ペイロード、コンテキスト プロパティ、メッセージング プロパティという 4 種類のイベント ソースからマップできます。 このトピックの手順では、オーケストレーション スケジュールからデータ項目をマップする方法について説明します。  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a>オーケストレーション スケジュールをイベント ソースとしてマップするには  
  
1.  既存の追跡プロファイルを開くか、新しい追跡プロファイルを作成します。 追跡プロファイルの作成の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。  
  
2.  クリックして、**イベント ソースの選択**(追跡プロファイル エディターの右側のペインの上にある) ボタンをクリックします。  
  
3.  選択、 **オーケストレーション スケジュール**カスケード メニューのメニュー項目。  
  
4.  オーケストレーションを含むアセンブリをクリックして、オーケストレーションの描画元の親アセンブリの選択、**アセンブリ名**ボックスの一覧し、をクリックして**次**です。  
  
     ![親アセンブリを TPE 内のイベント ソースとして選択](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")  
  
5.  データ項目のソースであるオーケストレーションを選択して、**オーケストレーション名**ボックスの一覧し、をクリックして**OK**です。  
  
6.  右ペインでデータ項目を選択し、左ペインにあるアクティビティの適切なノードにドラッグします。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)   
 [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)