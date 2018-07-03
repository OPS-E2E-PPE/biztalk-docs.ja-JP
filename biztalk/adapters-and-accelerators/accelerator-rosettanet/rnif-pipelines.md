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
ms.openlocfilehash: 9245517e9a333229912e6c18c3a48ea06eadf50a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988499"
---
# <a name="rnif-pipelines"></a>RNIF パイプライン
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信および送信パイプラインが受信に必要な処理を実行または RosettaNet Implementation Framework (RNIF) メッセージを送信します。 この処理には、事前処理、デコードとエンコード、暗号化の解除と暗号化、逆アセンブルとアセンブル、およびパーティ認証が含まれます。  
  
## <a name="pipeline-files"></a>パイプライン ファイル  
 標準[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信し、送信パイプラインがネイティブに RNIF メッセージを処理しない操作を行います。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 追加のカスタム受信および送信パイプラインをこの目的のためです。 これらのパイプラインは [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] パイプライン上に構築されていますが、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 固有の処理機能が追加されています。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン (RNIFReceive.btp および RNIFSend.btp) で使用可能な[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK \<*ドライブ*\>: \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。 これによって、独自の目的に合わせたパイプラインのカスタマイズが可能になります。  
  
## <a name="see-also"></a>参照  
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)