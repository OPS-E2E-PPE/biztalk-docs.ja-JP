---
title: BAM の追跡を無効化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, disabling BAM tracking
- BAM tracking
ms.assetid: ea5fef0e-7a96-46f5-81d8-9b1d8a5d24d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e734bd31147ecacc8bbbe98d98297edfb4f0de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209050"
---
# <a name="disabling-bam-tracking"></a>BAM 追跡を無効にします。
既定では、FIN 対応調整の BAM の追跡が有効にします。 無効にできますとおりです。  
  
### <a name="to-disable-bam-tracking-for-frr"></a>BAM FRR の追跡を無効にするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。  
  
2.  レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk Accelerator に移動します。  
  
    > [!IMPORTANT]
    >  FIN 対応調整がで実行されている各コンピューターでは、このレジストリ エントリを変更する必要があります。  
  
3.  レジストリ エディターの右側のウィンドウでダブルクリック**BAMTrackingEnabled**です。  
  
4.  **DWORD 値の編集** ダイアログ ボックスで、**値のデータ**ボックスに、入力**0** BAM の追跡を無効にします。  
  
5.  **[OK]** をクリックします。