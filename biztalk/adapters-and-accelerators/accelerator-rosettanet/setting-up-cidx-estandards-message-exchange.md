---
title: CIDX eStandards メッセージ交換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f1045e3a9562821c64e74df300ccbf9ab279d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281729"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>CIDX eStandards メッセージ交換
ここでは、Chemical Data Exchange (CIDX) eStandards メッセージ交換のセットアップ方法を説明します。 CIDX では、次の 3 つのプロパティが次のように設定されている必要があります。  
  
- `Standard` プロセス構成設定にプロパティ**CIDX**  
  
- プロセス構成設定の `Is Single Action` プロパティが `True` に設定されている。  
  
- `0A1 agreement` プロパティを取引先アグリーメントに**非 0A1**  
  
  CIDX と RosettaNet の違いについては、次を参照してください。 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)します。  
  
### <a name="to-set-up-cidx-message-exchange"></a>CIDX メッセージ交換をセットアップするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3. 右クリック**プロセス構成設定**、 をポイント**新規**、 をクリックし、**プロセス構成**します。  
  
4. 新しいプロセス構成のプロパティ ダイアログ ボックスで、上、**全般** タブの**標準**プロパティで、 **CIDX**。  
  
5. **アクティビティ** タブの**シングル アクション**プロパティで、 **True**。  
  
6. 必要に応じて、その他のプロセス構成設定を入力します。 これらの設定については、表を参照して[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。  
  
7. **[OK]** をクリックします。  
  
8. 右クリックして**契約**、 をポイント**新規**、順にクリックします**契約**します。  
  
9. **全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブで、さまざまな設定値を入力します。 これらの設定については、表を参照して[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。  
  
10. 新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般** タブの**0A1 アグリーメント**プロパティで、 **0A1**。  
  
11. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [パートナーの作成と編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)