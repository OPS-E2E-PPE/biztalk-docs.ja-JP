---
title: 手順 8 b:HI System 用のパーティ情報の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd7afd025337d10e5f18fad03ded58544ce07ff0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286595"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a>手順 8 b:HI System 用のパーティ情報を構成します。
この手順では、HI System 用のパーティ情報を構成します。  
  
### <a name="to-configure-the-hi-system-party-information"></a>HI System パーティ情報を構成するには  
  
1. BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
2. パーティのプロパティ ダイアログ ボックスでの**名前**フィールドに「 **HIS**します。 (このボックスに入力した値は、元の HL7 メッセージ インスタンス qry ^ q01.txt MSH5 を一致する必要があります)  
  
3. コンソール ツリーで、クリックして**送信ポート**します。  
  
4. **送信ポート**ウィンドウの**名前**最初の行では、次のように選択します。 **HIS_Send**、順にクリックします**OK**。  
  
   続行する[手順 9。BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)します。