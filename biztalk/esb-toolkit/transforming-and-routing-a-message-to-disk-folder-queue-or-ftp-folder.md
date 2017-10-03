---
title: "変換して、ディスクのフォルダー、キュー、または FTP フォルダーにメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eb767b588f5531e033ec0c867ee2c6dfad02bc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a>変換して、ディスクのフォルダー、キュー、または FTP フォルダーへのメッセージのルーティング
このユース ケースでは、ESB は、行程 Web サービスを通じて送信された、または、ランプでメッセージを変換します。 ファイルの種類の動的解決の参照、FTP、またはキューの場所は、マップの名前 (変換) と、メッセージのターゲット エンドポイントを図 1 に示すように決定します。  
  
 ![ディスク フォルダーの変換](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")  
  
 **図 1**  
  
 **変換して、ディスクのフォルダーへのメッセージのルーティング**  
  
 含まれる動的な解決サンプル[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 コンポーネントを使用して動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し、解決を実行する方法を示します[!INCLUDE[prague](../includes/prague-md.md)]オーケストレーションを使用せず、メッセージング レベルにマップします。 また、一方向と双方向の両方のメッセージング パターンを示します。  
  
 このユース ケースの拡張機能は、単純なルーティング ソリューション ファイル、FTP、または変換の追加のステップがない場合、キューの場所に、受信メッセージをルーティングします。  
  
 詳細については、次を参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)です。