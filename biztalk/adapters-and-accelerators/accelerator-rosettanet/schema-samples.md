---
title: "スキーマのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f8070c260c3972b2e8eef58af538932f1c5bf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="schema-samples"></a>スキーマのサンプル
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、一連 RNIF と PIP Partner Interface Process () の処理のための XSD スキーマにはが含まれています。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]これらのスキーマを使用して、メッセージを処理します。 これらのスキーマは目的に応じて変更したり、エラーのトラブルシューティングに使用したりできます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはスキーマが 3 セット用意されています。 これらのスキーマは、RosettaNet の PIP、RosettaNet の次世代スキーマ、および RNIF スキーマに関連付けられた XSD スキーマです。  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a>RosettaNet PIP に関連付けられた XSD スキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらのスキーマを使用して、メッセージ インスタンスのサービス コンテンツを検証します。 これらのスキーマを変更してメッセージの処理方法を変えることができます。 また、サービス コンテンツの処理中にエラーが発生した場合は、これらのスキーマを使用してメッセージを検証し、原因を突き止めることができます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらのスキーマが RNPIP アセンブリにコンパイルされています。 これらのスキーマのいずれかを変更する場合は、RNPIP アセンブリの展開を解除し、スキーマを変更してから RNPIP を再度展開します。 スキーマを変更しないように注意する必要があります。 スキーマを変更すると、対応する RosettaNet PIP に対応しなくなる可能性があります。 スキーマを RNPIP に追加することもできます。 詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator forRosettanet \sdk\schemas です。  
  
## <a name="rnif-schemas"></a>RNIF のスキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はこれらのスキーマを使用して、Preamble、Service Header、Delivery Header などの RNIF メッセージの構成要素を検証します。 また、これらには受信確認と例外のスキーマも含まれています。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for\Sdk\rnifschemas です。  
  
## <a name="rosettanet-next-generation-schemas"></a>RosettaNet の次世代スキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はこれらのスキーマを使用して、メッセージが RosettaNet の次世代スキーマに準拠しているかどうかを検証します。 これらのスキーマは、DTD ではなく XSD をネイティブでサポートしています。 使用するにはこれらのスキーマに追加、Rnpip アセンブリ」の説明に従って[Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで、 \<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator forRosettaNet\SDK\Schemas\Domain \domain、\Interchange、および \Universal フォルダーです。  
  
## <a name="see-also"></a>参照  
 [PIP の実装](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)   
 [Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [サンプル](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)