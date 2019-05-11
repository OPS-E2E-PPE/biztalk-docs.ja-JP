---
title: パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70dd783e805116b24e224886e02d0f46fe2edfed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281824"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウトの設定
同期のシナリオで HTTP アダプターを使用したパブリック プロセス オーケストレーションを使用するときにごとのタイムアウトの設定値を適切に設定する必要があります。 オーケストレーション (実行までの時間) のタイムアウト設定は、(要求タイムアウト) HTTP アダプターのタイムアウトより小さくする必要があります。 これは、ため、アダプターが、オーケストレーションの前にタイムアウトになる可能性があります、HTTP アダプターの設定が小さい場合は、です。 これにより、プロセス、アダプターを制御します。 オーケストレーションがプロセスのコントロールである必要があります。そのため、そのタイムアウトの設定は、小さくする必要があります。  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>HTTP アダプターのタイムアウトを設定するには  
  
1.  BizTalk エクスプ ローラーで、**送信ポート**、パブリック プロセス オーケストレーションを使用する HTTP 送信ポートをダブルクリックします。  
  
2.  送信ポートのプロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) の**アドレス (URI)** します。  
  
3.  HTTP トランスポートのプロパティ ウィンドウの 全般 ウィンドウで、**要求のタイムアウト (秒)** ボックスに、適切なタイムアウト値を入力します。この値はより大きくする必要があります、**実行までの時間**の関連するプロセス PIP (Partner Interface) を設定します。  
  
4.  をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>パブリック プロセス オーケストレーションのタイムアウト設定を設定するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**BizTalk Accelerator for RosettaNet 管理コンソール**します。  
  
2. 展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**プロセス構成設定**します。  
  
3. タイムアウトを設定を設定する PIP を右クリックし、をクリックし、**プロパティ**します。  
  
4. プロパティ ダイアログ ボックスで、上、**アクティビティ** タブで、**実行までの時間**ボックスで、適切な値を設定すると、HTTP アダプターのタイムアウトよりも小さいを入力し、をクリックし、 **ok**.  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)