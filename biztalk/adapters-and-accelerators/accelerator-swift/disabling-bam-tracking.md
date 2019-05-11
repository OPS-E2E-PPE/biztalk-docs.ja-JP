---
title: BAM の追跡を無効にする |Microsoft Docs
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
ms.openlocfilehash: c70760db419ac11386e0cfa83b85b89fdd0bc63f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378053"
---
# <a name="disabling-bam-tracking"></a>BAM 追跡を無効にします。
既定では、FIN Response Reconciliation の BAM の追跡が有効にします。 次のように無効することができます。  
  
### <a name="to-disable-bam-tracking-for-frr"></a>BAM FRR の追跡を無効にするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。  
  
2.  レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk アクセラレータに移動します。  
  
    > [!IMPORTANT]
    >  FIN Response Reconciliation がで実行されている各コンピューターでこのレジストリ エントリを変更する必要があります。  
  
3.  レジストリ エディターの右側のウィンドウでダブルクリック**BAMTrackingEnabled**します。  
  
4.  **DWORD 値の編集** ダイアログ ボックスで、**値データ**ボックスに「 **0** BAM 追跡無効にします。  
  
5.  **[OK]** をクリックします。