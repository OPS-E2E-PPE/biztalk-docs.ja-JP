---
title: 設定を CIDX eStandards メッセージ交換 |Microsoft ドキュメント
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
ms.openlocfilehash: 4c4606dfc4b912d884a997bb65acb26cb4352448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>設定を CIDX eStandards メッセージ交換
ここでは、Chemical Data Exchange (CIDX) eStandards メッセージ交換のセットアップ方法を説明します。 CIDX では、次の 3 つのプロパティが次のように設定されている必要があります。  
  
-   `Standard`プロセス構成設定にプロパティ**CIDX**  
  
-   プロセス構成設定の `Is Single Action` プロパティが `True` に設定されている。  
  
-   `0A1 agreement`プロパティを取引先アグリーメントに**非 0A1**  
  
 CIDX と RosettaNet の違いの詳細については、次を参照してください。 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)です。  
  
### <a name="to-set-up-cidx-message-exchange"></a>CIDX メッセージ交換をセットアップするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  右クリック**プロセス構成設定**、 をポイント**新規**、クリックして**プロセス構成**です。  
  
4.  新しいプロセス構成のプロパティ ダイアログ ボックスで、**全般** タブの**標準**プロパティを選択**CIDX**です。  
  
5.  **アクティビティ** タブの**シングル アクション**プロパティで、 **True**です。  
  
6.  必要に応じて、その他のプロセス構成設定を入力します。 これらの設定については、表を参照して[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)です。  
  
7.  **[OK]**をクリックします。  
  
8.  右クリック**契約**、 をポイント**新規**、クリックして**アグリーメント**です。  
  
9. **全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブは、さまざまな設定の値を入力します。 これらの設定については、表を参照して[を作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)です。  
  
10. 新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般** タブの**0A1 アグリーメント**プロパティを選択**非 0A1**です。  
  
11. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [作成またはパートナーを編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)