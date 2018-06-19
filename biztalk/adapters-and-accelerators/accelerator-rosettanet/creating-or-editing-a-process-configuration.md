---
title: 作成または編集のプロセスの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- creating, process configuration
- modifying, process configuration
ms.assetid: 39cc2c93-0986-48d3-8c6f-4280ec9af4e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9130ab7370f8f6e1fcbe75bc7a85a6c74dfe328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207122"
---
# <a name="creating-or-editing-a-process-configuration"></a>作成またはプロセス構成を編集します。
このセクションを作成または構成を編集するプロセス、プロセス PIP (Partner Interface) で実装する方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。 RosettaNet PIP は、2 つの取引先間におけるビジネス プロセス ダイアログを定義します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パートナーと PIP を作成するには、プロセス構成を作成する必要があります。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]PIP のすべての構成の特徴を格納するのにには、このプロファイルを使用します。 この構成は、パートナーとのアグリーメントの作成に使用できます。  
  
 プロセス構成のプロパティ、および作成またはプロセス構成を編集するための手順については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)です。  
  
 新しいプロセス構成を作成する場合は、RosettaNet 組織によって管理される PIP 仕様ドキュメントに基づいた設定を行う必要があります。 すべてのプロセス構成設定は PIP 仕様に従って行われ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、ほとんどの設定に既定値 (そのフィールドに最も一般的に使用される値) が使用されます。 設定が適切な PIP 仕様の値に対応することを必ず確認してください。 入力した PIP 設定が PIP 仕様のガイダンスにマップする方法の詳細については、次を参照してください。 [PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)です。  
  
 プロセス構成は、RosettaNet または CIDX (Chemical Industry Data Exchange) のどちらにも構成できます。 CIDX の構成については、次を参照してください。[設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、プロセスがアクティブな間はプロセス構成を変更できません。 プロセス構成を変更すると、アクティブなプロセスは失敗に終わります。 プロセスを新しくすると、どのプロセスも新しい構成設定を正常に取得します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [PIP 仕様を使用して、プロセス構成を作成するには](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)