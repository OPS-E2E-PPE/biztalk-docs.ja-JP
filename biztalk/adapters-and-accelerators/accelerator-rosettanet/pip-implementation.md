---
title: PIP の実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs
- PIPs, element-level constraints
- Document Type Definitions (DTDs)
- PIPs, schemas
- examples, schemas
- schemas, examples
- PIPs, about PIPs
- element-level constraints
- PIPs, DTDs
- schemas, PIPs
- XML Schema Definition files (XSDs)
- Partner Interface Processes (PIPs)
- DTDs, XSDs
- schemas, XSDs
ms.assetid: 0d964223-e0b6-4377-b26a-5fdc89ec81f4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8105cabdb5019cc706abfd8624de6cef76f9179
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282951"
---
# <a name="pip-implementation"></a>PIP 実装
RosettaNet Partner Interface Process (Pip) は、サプライ チェーン内の取引先間のビジネス プロセスを定義します。 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]一連の Pip のボックスのことができますを作成して Pip を追加します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RosettaNet 組織で定義されているすべての Pip をサポートしています。  
  
 詳細については、次を参照してください。 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)します。  
  
## <a name="schemas-in-btarn"></a>BTARN のスキーマ  
 RosettaNet は、文書型定義 (DTD) の形式で PIP メッセージ スキーマをすべて指定します。 ビジネス ドキュメントを交換する取引先は、これらの DTD に準拠している必要があります。 ただし、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Microsoft BizTalk Server は、Dtd ではなく Xsd を使用してドキュメントを表すために、これらの Dtd を XML スキーマ定義ファイル (Xsd) として実装します。 機能面では XSD が DTD に優先しており、XSD はメッセージ ガイドラインに提供されるほとんどの情報をネイティブに表すことができます。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、最近 RosettaNet 組織によって発行された、XSD 仕様を使用する次世代の PIP もサポートします。  
  
 新しい PIP を実装するためには、PIP の DTD を XSD へ変換する必要があります。 RosettaNet の Web サイトから PIP に関連付けられている DTD をダウンロードする[ http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)します。 次に、PIP に基づく [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プロセス構成プロファイルを作成します。 詳細については、次を参照してください。[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)します。  
  
 既存のプロファイルに基づいて、新しいプロセス構成プロファイルを作成できます。 詳細については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。 1 つのプロセス構成プロファイルに基づいて、同じパートナー間で複数のアグリーメントを作成できます。 ただし、アクティブ化できるアグリーメントは一度に 1 つだけです。 作成し、アグリーメントをアクティブ化を参照してください。[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、以下の RosettaNet ヘッダーに対して RosettaNet メッセージ ガイドラインの制約を適用して XSD を実装します。  
  
-   RNIF 1.1 および RNIF 2.01 の Preamble  
  
-   RNIF 1.1 および RNIF 2.0 の Service Header  
  
-   RNIF 2.0 の Delivery Header  
  
-   RNIF 1.1 および RNIF 2.01 のすべてのシグナル メッセージの Service Content  
  
## <a name="sample-schemas"></a>サンプル スキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] セットアップのインストールに Pip のセット\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas します。 これらはサンプルとしてのみ使用します。 実際に使用する前に、これらのスキーマを公開された最新の RosettaNet PIP 仕様およびメッセージ ガイドラインと照らし合わせることを強くお勧めします。 BTARN は、すべての RosettaNet PIP の実装をサポートします。  
  
## <a name="element-level-constraints-in-btarn"></a>BTARN の要素レベルの制約  
 BTARN では、PIP メッセージ ガイドライン文書で指定されている要素レベルの制約をプロセス構成の設定として実装します。 ランタイム コンポーネントはプロセス構成を使用して、特定の PIP の処理方法を決定します。  
  
 新しい PIP を実装するためには、新しいプロセス構成プロファイルを作成して、PIP にメッセージ ガイドライン制約を適用する必要があります。 この操作は BTARN 管理コンソールで行います。 詳細については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。  
  
 プロセス構成プロファイルは、のように、RosettaNet PIP 仕様にマップ[PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [取引先アグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md)   
 [RosettaNet PIP](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)
