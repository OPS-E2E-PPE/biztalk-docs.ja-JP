---
title: RNIF パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNIF, pipelines
- pipelines, RNIF
ms.assetid: 6cf480fe-6b54-4b13-8318-617f3bba71d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 458eeed6643aa6f8ea5211f517b33a6886d3e756
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282354"
---
# <a name="rnif-pipelines"></a>RNIF パイプライン
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信および送信パイプラインが受信に必要な処理を実行または RosettaNet Implementation Framework (RNIF) メッセージを送信します。 この処理には、前処理、デコード、エンコード、暗号化/復号化、逆アセンブルとアセンブル、およびパーティの認証が含まれています。  
  
## <a name="pipeline-files"></a>パイプライン ファイル  
 標準[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信し、送信パイプラインがネイティブに RNIF メッセージを処理しない操作を行います。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 追加のカスタム受信および送信パイプラインをこの目的のためです。 これらのパイプラインは上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]パイプラインが追加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-特定の処理機能。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン (RNIFReceive.btp および RNIFSend.btp) で使用可能な[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK \<*ドライブ*\>: \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。 これにより、独自の目的に合わせてカスタマイズできます。  
  
## <a name="see-also"></a>参照  
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)