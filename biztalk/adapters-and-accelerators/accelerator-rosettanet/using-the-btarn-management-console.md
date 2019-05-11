---
title: BTARN 管理コンソールの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, activating
- activating agreements
- BTARN Management Console, Scope pane
- tracking
- creating, trading partners
- BTARN Management Console, agreements
- process configuration
- agreements, modifying
- BTARN Management Console, home organizations
- agreements, creating
- BTARN Management Console, trading partners
- agreements, deleting
- deleting, agreements
- BTARN Management Console
- agreements, listing
- modifying, trading partners
- creating, agreements
- trading partners, creating
- modifying, agreements
- BAM tracking
- Scope pane [BTARN Management Console]
- trading partners, modifying
- trading partners, deleting
- BTARN Management Console, process configurations
- deleting, trading partners
- BTARN Management Console, about BTARN Management Console
- home organizations
ms.assetid: 000ee93d-eb1d-4ff8-a9cf-0547beff027d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d3d9b481a2026181355c68fcfa05c19c44b5405
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299993"
---
# <a name="using-the-btarn-management-console"></a>BTARN 管理コンソールの使用
ここでは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を管理する方法について説明します。  
  
 開く、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールをクリックして**開始**をポイントして、**プログラム**をポイントして、 **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]をクリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールのスコープ (左) ペインには、すべての [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成ノードが含まれます。 結果 (右) ペインには、スコープ ペインで選択した構成項目の特定のインスタンスがすべて含まれます。  
  
## <a name="operations-in-the-scope-pane"></a>スコープ ペインでの操作  
 スコープ ペイン内のノードについて、次の操作を実行できます。  
  
- パートナー送信ポートで使用する [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送受信パイプラインを設定します。 詳細については、次を参照してください。[設定 BTARN 送信パイプラインと受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)します。  
  
- ビジネス アクティビティ監視 (BAM) の追跡を有効にします。 詳細については、次を参照してください。 [BAM の追跡を有効にする](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)します。  
  
- 新しくインポートした構成をスコープ ペインで、[構成] ノードを右クリックし、をクリックして、コンソールに表示されることを確認**更新**します。  
  
- 右クリックし、結果ウィンドウで、追加の列を表示、**プロセス構成設定**または**契約**を指す、スコープ ペインでノード**ビュー**、し、クリックすると**列の追加/削除**します。 使用して、使用可能な列と表示されている列の間で列を移動、**を追加または削除**ボタンをクリックします。 このコマンドは、既定では [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に表示されませんが、使用できる列が多数あるアグリーメントで特に役に立ちます。  
  
## <a name="process-configurations"></a>プロセス構成  
 プロセス構成設定について、次の操作を実行できます。  
  
-   右クリックして新しいプロセス構成を追加、**プロセス構成設定**スコープ ノードを指す**新規**、 をクリックし、**プロセス構成**します。 詳細については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。  
  
-   結果ウィンドウでプロセス構成を右クリックし、をクリックして既存のプロセス構成を編集**プロパティ**、またはプロセス構成をダブルクリックします。 詳細については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。  
  
-   結果ウィンドウでプロセス構成を右クリックし、をクリックして既存のプロセス構成を削除**削除**します。  
  
-   新しい構成を基準とする結果ウィンドウで、構成を右クリックし、をクリックして、既存のプロセス構成に基づいて、新しいプロセス構成を作成**コピーから新しいプロセス構成**. これにより、新しい表示されます**プロセス構成のプロパティ**が設定された、既存の構成 ダイアログ ボックス。 新しい入力**コードを表示**、順にクリックします**OK**新しい構成を作成します。 詳細については、次を参照してください。 [PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)します。  
  
-   結果ウィンドウで特定の構成を右クリックし、をクリックして、プロセス構成が関連付けられているすべての契約の一覧を表示する**を表示する契約**します。 フォーカスを移すこれは、**契約**スコープ ペインでノードし、結果ウィンドウで、関連付けられているアグリーメントを表示します。 右クリックし、アグリーメントの完全な一覧に戻すことができます、**契約**スコープ ウィンドウで、クリックすると、ノード**すべて表示**します。  
  
## <a name="home-organizations"></a>ホーム組織  
 ホーム組織について、次の操作を実行できます。  
  
-   右クリックして新しいホーム組織を追加、**ホーム組織**スコープ ノードを指す**新規**、 をクリックし、**ホーム組織**します。 詳細については、次を参照してください。[を作成または編集、ホーム組織](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)します。  
  
-   結果ウィンドウでホーム組織を右クリックし、をクリックして既存のホーム組織を編集**プロパティ**、ホーム組織をダブルクリックして、します。 詳細については、次を参照してください。[を作成または編集、ホーム組織](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)します。  
  
-   結果ウィンドウでホーム組織を右クリックし、をクリックして既存のホーム組織を削除**削除**します。  
  
## <a name="partners"></a>パートナー  
 パートナーについて、次の操作を実行できます。  
  
-   右クリックして新しいパートナーを追加、**パートナー**スコープ ノードを指す**新規**、 をクリックし、**パートナー**します。 詳細については、次を参照してください。[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)します。  
  
-   結果ウィンドウで、パートナーを右クリックし、をクリックして既存のパートナーを編集**プロパティ**、または、パートナーをダブルクリックします。 詳細については、次を参照してください。[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)します。  
  
-   結果ウィンドウで、パートナーを右クリックし、をクリックして既存のパートナーを削除**削除**します。  
  
## <a name="agreements"></a>契約  
 アグリーメントについて、次の操作を実行できます。  
  
-   右クリックして新しい契約を追加、**契約**スコープ ノードを指す**新規**、 をクリックし、**契約**します。 詳細については、次を参照してください。[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。  
  
-   結果ウィンドウで、アグリーメントを右クリックし、をクリックして既存のアグリーメントを編集**プロパティ**、または、アグリーメントをダブルクリックします。 詳細については、次を参照してください。[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。  
  
-   結果ウィンドウで、アグリーメントを右クリックし、をクリックして既存のアグリーメントを削除**削除**します。  
  
-   結果ウィンドウで、非アクティブ化されたアグリーメントを右クリックし、をクリックしてアグリーメントをアクティブ化**Activate**します。 これにより、送信または受信されるアグリーメントに関連付けられたメッセージが有効になります。 アグリーメントに関連付けられたメッセージが送信または受信されないように、アグリーメントを非アクティブ化することもできます。  
  
-   プロセス構成が関連付けられているアグリーメントだけの一覧を表示した後は、アグリーメントの完全な一覧に戻すを右クリックし、**契約**スコープ ウィンドウで、クリックすると、ノード**すべて表示**.  
  
## <a name="see-also"></a>参照  
 [BTARN 送信の設定および受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)   
 [BAM 追跡を有効にします。](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)   
 [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [アグリーメントの作成と編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)