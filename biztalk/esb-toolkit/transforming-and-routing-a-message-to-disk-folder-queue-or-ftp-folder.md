---
title: 変換して、ディスク フォルダー、キュー、または FTP フォルダーへのメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfed87c48e0e8dfc845163325319f77de1bc2dff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399636"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a>変換して、ディスク フォルダー、キュー、または FTP フォルダーへのメッセージのルーティング
このユース ケースでは、ESB は、旅行プランの Web サービスを通じて送信された、または、ランプでメッセージを変換します。 ファイルの種類の動的解決のルックアップ、FTP、またはキューの場所は、(変換) のマップの名前と、メッセージの対象のエンドポイントを図 1 に示すように決定します。  
  
 ![ディスクのフォルダーの変換](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")  
  
 **図 1**  
  
 **変換して、ディスク フォルダーへのメッセージのルーティング**  
  
 動的解決サンプルに含まれている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 コンポーネントを使用して動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し解決およびオーケストレーションを使用しなくても、メッセージング レベルで maps に BizTalk Server を実行する方法を示します。 一方向と双方向の両方のメッセージング パターンも示します。  
  
 このユース ケースの拡張機能は、ファイル、FTP、または変換の追加の手順を使用せず、キューの場所に、受信メッセージをルーティングする単純なルーティング ソリューションです。  
  
 詳細については、次を参照してください。[をインストールすると、動的解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)します。