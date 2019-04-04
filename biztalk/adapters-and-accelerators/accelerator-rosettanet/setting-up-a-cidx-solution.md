---
title: CIDX ソリューションのセットアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770691b2862aba307e6f1cc444c8d38adce4aeb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984291"
---
# <a name="setting-up-a-cidx-solution"></a>CIDX ソリューションの設定
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] は、CIDX (Chemical Industry Data Exchange) XML メッセージ交換 (CIDX Chem eStandards バージョン 2.0 および 3.0) をサポートしています。 ここでは、次の操作を行って CIDX ソリューションを設定する方法について説明します。  
  
-   プロセス構成の設定  
  
-   アグリーメントの設定  
  
-   PIP の適用  
  
-   XSD ベース PIP のインポート  
  
-   Elemica ネットワークへの接続  
  
## <a name="setting-up-a-cidx-process-configuration"></a>CIDX プロセス構成の設定  
 CIDX eStandards メッセージ交換を設定するには、次のプロパティを持つプロセス構成を作成する必要があります。  
  
- **標準**プロパティに設定するプロセス構成設定で**CIDX**  
  
- **シングル アクション**プロパティに設定するプロセス構成設定で**は True。**  
  
- **0A1 アグリーメント**プロパティ設定する取引先パートナー アグリーメントで**非 0A1**  
  
  詳細については、[を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)を参照してください。  
  
## <a name="creating-a-cidx-agreement"></a>CIDX アグリーメントの作成  
 CIDX eStandards メッセージ交換を設定するには、次のプロパティを持つアグリーメントを作成する必要があります。  
  
- **RNIF バージョン**プロパティに設定するアグリーメントの設定で**V01.10.00**  
  
- **0A1 アグリーメント**プロパティに設定するアグリーメントの設定で**非 0A1**  
  
  詳細については、[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)を参照してください。  
  
## <a name="applying-a-pip-for-cidx"></a>CIDX 用 PIP の適用  
 PIP を CIDX 実装に適用するには、設定、**標準**にプロセス構成プロファイルのプロパティ**CIDX**します。 完了したら後の値を入力できるが、**メッセージ標準**、**標準バージョン**、および**ペイロードのバインド ID**します。 これらの値は CIDX Chem eStandards の仕様に含まれています。  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a>CIDX 用 XSD ベース PIP のインポート  
 CIDX 用、XSD ベース PIP をインポートするには、CIDX.org から PIP の ZIP ファイルをダウンロードする必要があります[ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)します。 説明されているインポート手順に従います[XSD ベース PIP のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)します。  
  
## <a name="connecting-to-the-elemica-network"></a>Elemica ネットワークへの接続  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] をカスタマイズし、Elemica Connectivity Pack のプロジェクト ファイルを使用して Elemica に接続できます。 Connectivity Pack をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195)します。 詳細については、MSDN のページで、"BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続 』 ホワイト ペーパーを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539)します。  
  
> [!NOTE]
>  [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] に対して、ホワイト ペーパー『BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続』の情報は有効です。  
  
## <a name="see-also"></a>参照  
 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)   
 [CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)   
 [CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [XSD ベース PIP のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)