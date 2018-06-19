---
title: パブリック プロセス オーケストレーションと HTTP アダプターのタイムアウトの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 339f4eb5fa11b23602d05f8cd75c30ca3aa16279
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963296"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>パブリック プロセス オーケストレーションと HTTP アダプターのタイムアウトの設定
同期接続シナリオでパブリック プロセス オーケストレーションを HTTP アダプターと一緒に使用する場合、それぞれのタイムアウトを適切に設定する必要があります。 オーケストレーションのタイムアウト設定 (実行までの時間) は HTTP アダプターのタイムアウト (要求のタイムアウト) より小さくする必要があります。 これは、HTTP アダプターの設定が小さいと、オーケストレーションの前にアダプターがタイムアウトになる可能性があるからです。 この場合、プロセスの制御権がアダプターに渡ります。 プロセスはオーケストレーションが制御する必要があるため、そのタイムアウト値が小さくなければなりません。  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>HTTP アダプターのタイムアウトを設定するには  
  
1.  BizTalk エクスプ ローラーで、**送信ポート**、し、パブリック プロセス オーケストレーションで使用する HTTP 送信ポートをダブルクリックします。  
  
2.  [送信ポートのプロパティ] ウィンドウの省略記号ボタン (**.**) の**アドレス (URI)** です。  
  
3.  HTTP トランスポートのプロパティ] ウィンドウの [全般] ウィンドウで、[、**要求のタイムアウト (秒)** ボックスに、タイムアウトの適切な値を入力します。この値はより大きくする必要があります、**実行までの時間**の関連するプロセス PIP (Partner Interface) を設定します。  
  
4.  をクリックして **[ok]**、順にクリック**OK**もう一度です。  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>パブリック プロセス オーケストレーションのタイムアウトを設定するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**BizTalk Accelerator for RosettaNet 管理コンソール**です。  
  
2.  展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、クリックして**プロセス構成設定**です。  
  
3.  タイムアウトを設定を設定する PIP を右クリックし、をクリックして**プロパティ**です。  
  
4.  プロパティ ダイアログ ボックスで、上、**アクティビティ**] タブの [、**実行までの時間**ボックスを設定すると、HTTP アダプタのタイムアウトよりも小さいを適切な値を入力してをクリックして **[ok]**.  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)