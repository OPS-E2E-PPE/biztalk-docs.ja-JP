---
title: "非推奨の MSMQT |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a>非推奨の MSMQT
MSMQT 機能は BizTalk Server から削除されました。 オーケストレーション デザイナーで、MSMQT トランスポート オプションは、デザイン時のポート構成ウィザードを選択すると次の図に示すように、**今指定**オプションを**ポートのバインド**.  
  
 **MSMQT トランスポートを示すポート構成ウィザード**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>BizTalk Server プロジェクト  
 新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトでは MSMQT トランスポート オプションを使用しないでください。 アプリケーション展開[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]は、エラーで失敗**プロトコルの種類"MSMQT"が見つかりません。**です。  
  
## <a name="migrated-biztalk-server-projects"></a>移行済み BizTalk Server プロジェクト  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトに移行できる[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に記載されている変換ウィザード[BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)です。 MSMQT トランスポートを使用するように構成されたポートを含むプロジェクトは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] への展開の前に手動で再構成する必要があります。 推奨される再構成は、MSMQ アダプターを使用する構成です。  MSMQ アダプターの詳細については、次を参照してください。 [MSMQ アダプターは何ですか?](../core/what-is-the-msmq-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [MSMQT アダプターから MSMQ アダプターへの移行](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)