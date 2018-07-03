---
title: CIDX サポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57500dc25e719d7ef693975b74850cbc04289dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997811"
---
# <a name="cidx-support"></a>CIDX サポート
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] CIDX (Chemical Industry Data Exchange) XML メッセージ交換のサポートを提供します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] CIDX Chem eStandards バージョン 2.0 および 3.0 では、RosettaNet 実装 Framework (RNIF) 1.1 を使用して、どちらもサポートしています。  
  
 シングル アクションとダブル アクションのメッセージをサポートしている [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の単純な非同期パブリック プロセスは、CIDX の Service Content を消費して、ルーティングします。  
  
 CIDX PIP に基づくアグリーメントについて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ではメッセージ内の以下の要素を検証します。  
  
- RNIF 1.1 バージョンのみ  
  
- 非 0A1  
  
- シングル アクションのみ  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 設定から妨げません、 `Standard` "CIDX"に設定した後にプロセス構成のプロパティ、 `0A1 agreement` (は CIDX のサポートされていません)"0A1"には、そのプロファイルを使用して、アグリーメントのプロパティ。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] これを禁止するクロス フィールド検証は実行されません。  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a>PIP の CIDX 実装への適用  
 PIP を CIDX 実装に適用するには、設定、`Standard`にプロセス構成プロファイルのプロパティ**CIDX**します。 メッセージ標準、標準のバージョン、およびペイロード バインド id。 の値を入力したらができます。 これらの値は CIDX Chem eStandards の仕様に含まれています。  
  
## <a name="connecting-to-the-elemica-network"></a>Elemica ネットワークへの接続  
 Microsoft のインストールを有効にすることができます[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、Elemica に接続する[!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)]Provider (ESP)。 Elemica ネットワークで CIDX メッセージ交換を使用することで、化学工業分野における購入、売却、サプライチェーン管理を行うことができます。  
  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] をカスタマイズし、Elemica Connectivity Pack のプロジェクト ファイルを使用して Elemica に接続します。 Connectivity Pack をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195)します。 詳細については、MSDN のページで、"BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続 』 ホワイト ペーパーを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539)します。  
  
> [!NOTE]
>  [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] に対して、ホワイト ペーパー『BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続』の情報は有効です。  
  
## <a name="cidx-procedures"></a>CIDX の手順  
 CIDX メッセージ交換の設定方法については、次のセクションで説明します。  
  
-   [CIDX eStandards メッセージ交換のセットアップ](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [アグリーメントの作成と編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [XSD ベース PIP のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)