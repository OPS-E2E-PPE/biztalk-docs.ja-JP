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
ms.openlocfilehash: f346d2e7258c14e09dbcdc5f29ff0f7690cb4a4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-samples"></a>スキーマのサンプル
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、一連 RNIF と PIP Partner Interface Process () の処理のための XSD スキーマにはが含まれています。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]これらのスキーマを使用して、メッセージを処理します。 これらのスキーマは目的に応じて変更したり、エラーのトラブルシューティングに使用したりできます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはスキーマが 3 セット用意されています。 これらのスキーマは、RosettaNet の PIP、RosettaNet の次世代スキーマ、および RNIF スキーマに関連付けられた XSD スキーマです。  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a>RosettaNet PIP に関連付けられた XSD スキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらのスキーマを使用して、メッセージ インスタンスのサービス コンテンツを検証します。 これらのスキーマを変更してメッセージの処理方法を変えることができます。 また、サービス コンテンツの処理中にエラーが発生した場合は、これらのスキーマを使用してメッセージを検証し、原因を突き止めることができます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらのスキーマが RNPIP アセンブリにコンパイルされています。 これらのスキーマのいずれかを変更する場合は、RNPIP アセンブリの展開を解除し、スキーマを変更してから RNPIP を再度展開します。 スキーマを変更しないように注意する必要があります。 スキーマを変更すると、対応する RosettaNet PIP に対応しなくなる可能性があります。 スキーマを RNPIP に追加することもできます。 詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for rosettanet \sdk\schemas です。  
  
## <a name="rnif-schemas"></a>RNIF のスキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はこれらのスキーマを使用して、Preamble、Service Header、Delivery Header などの RNIF メッセージの構成要素を検証します。 また、これらには受信確認と例外のスキーマも含まれています。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for \sdk\rnifschemas です。  
  
## <a name="rosettanet-next-generation-schemas"></a>RosettaNet の次世代スキーマ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はこれらのスキーマを使用して、メッセージが RosettaNet の次世代スキーマに準拠しているかどうかを検証します。 これらのスキーマは、DTD ではなく XSD をネイティブでサポートしています。 使用するにはこれらのスキーマに追加、Rnpip アセンブリ」の説明に従って[Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによって、これらのスキーマで、 \<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for RosettaNet\SDK\Schemas\ドメイン、\Interchange、および \Universal フォルダーです。  
  
## <a name="see-also"></a>参照  
 [PIP の実装](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)   
 [Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [サンプル](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)