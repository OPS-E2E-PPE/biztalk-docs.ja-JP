---
title: 非推奨の MSMQT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a54e775d9a7f683b11440f1d6ad0e43bdbecb43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263640"
---
# <a name="msmqt-deprecation"></a>非推奨の MSMQT
MSMQT 機能は BizTalk Server から削除されました。 オーケストレーション デザイナーでは MSMQT トランスポート オプションは選択すると次の図で示すようにデザイン時のポート構成ウィザードで使用できる、**今指定する**オプション**ポートのバインド**.  
  
 **MSMQT トランスポートを示すポート構成ウィザード**  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a>BizTalk Server プロジェクト  
 新しい[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトでは、MSMQT トランスポート オプションを使用しないでください。 アプリケーションの展開を BizTalk Server は、エラーで失敗**プロトコルの種類"MSMQT"が見つかりません。** します。  
  
## <a name="migrated-biztalk-server-projects"></a>移行済み BizTalk Server プロジェクト  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを使用して BizTalk Server に移行できる、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に記載されている変換ウィザード[BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)します。 MSMQT トランスポートを使用するように構成するポートを含むプロジェクトは、BizTalk Server に展開する前に手動で再構成する必要があります。 推奨される再構成では、MSMQ アダプターを使用します。  MSMQ アダプターの詳細については、次を参照してください。 [MSMQ アダプターとは何ですか?](../core/what-is-the-msmq-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [MSMQT アダプターから MSMQ アダプターへの移行](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)