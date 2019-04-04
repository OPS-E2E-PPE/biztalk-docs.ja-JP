---
title: 作成またはプロセス構成の編集 |Microsoft Docs
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
ms.openlocfilehash: 32300e84d2c9102baaa68a57045fefc103d0d9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013163"
---
# <a name="creating-or-editing-a-process-configuration"></a>作成またはプロセス構成の編集
このセクションは、Microsoft では、プロセス PIP (Partner Interface) を実装するためにプロセス構成を作成または更新する方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 RosettaNet PIP は、2 つの取引先間におけるビジネス プロセス ダイアログを定義します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パートナーと PIP を作成するのには、プロセス構成を作成する必要があります。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] PIP のすべての構成特性を格納するのにには、このプロファイルを使用します。 この構成は、パートナーとのアグリーメントの作成に使用できます。  
  
 プロセス構成のプロパティ、および作成またはプロセス構成を編集するための手順については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。  
  
 新しいプロセス構成を作成する場合は、RosettaNet 組織によって管理される PIP 仕様ドキュメントに基づいた設定を行う必要があります。 すべてのプロセス構成設定は PIP 仕様に従って行われ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、ほとんどの設定に既定値 (そのフィールドに最も一般的に使用される値) が使用されます。 設定が適切な PIP 仕様の値に対応することを必ず確認してください。 入力した PIP 設定が PIP 仕様のガイダンスへマップする方法の詳細については、[PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)を参照してください。  
  
 プロセス構成は、RosettaNet または CIDX (Chemical Industry Data Exchange) のどちらにも構成できます。 CIDX の構成については、[を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)を参照してください。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、プロセスがアクティブな間はプロセス構成を変更できません。 プロセス構成を変更すると、アクティブなプロセスは失敗に終わります。 プロセスを新しくすると、どのプロセスも新しい構成設定を正常に取得します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロセス構成を作成または編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [PIP 仕様を使用したプロセス構成の作成](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [承認プロパティと否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [CIDX eStandards メッセージ交換のセットアップ](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)