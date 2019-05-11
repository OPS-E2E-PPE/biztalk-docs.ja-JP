---
title: InfoPath のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2797cd51e6e013feb6c273b3aace8a007d71a4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377395"
---
# <a name="infopath-security"></a>InfoPath のセキュリティ
Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 では、XML 署名を使用して、デジタル証明書を使用してフォームにデジタル署名することができます。 XML 署名は、XML ドキュメントに含まれるデータを保護するために使用する XML ベースのデジタル署名用の標準を定義します。 XML 署名は、標準の World Wide Web Consortium (W3C) によって管理されます。  
  
 デジタル署名は、マクロ、またはドキュメントでの認証のスタンプを電子的、セキュリティで保護された、暗号化ベースです。 デジタル署名するときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、フォームを使用して入力 XML インスタンスが「スタンプ」デジタル署名 (signature パブリック キーと署名済みデータ ダイジェストは、XML で、専用のノードに書き込まれます)。 この署名は、XML ドキュメントが署名者、改ざんされていないことを確認します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 署名の検証可能な否認不可能で、部分署名、cosigning と副強化されたデジタル署名のサポートを提供します。  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT によって提供される FormGenerator ユーティリティで生成されたフォームでは、デジタル署名の countersigning メソッドを使用して、互いの上に重ねられます countersigners の署名を使用します。 この countersigning 署名スタックの作成または SWIFT メッセージの編集、レビューおよび承認した 1 つ以上のレビュー担当者と、承認者のメッセージが含まれる、および最後にそのメッセージを送信するワークフローのすべてのステージの後にのみ、人間指向のプロセスをモデル化します。サインオフします。  
  
 Repairers、レビュー担当者、または承認者は、承認または拒否するかどうかに関係なくメッセージに署名します。 署名は、応答の信頼性を示すし、「承認済み」の意思決定を必ずしも意味しません。  
  
 ときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームが送信される、メッセージの有効性をチェックおよび適切なロールで、ユーザーがフォームへの署名があります。  
  
 (修復) だけでなく、ワークフローで何らかの段階で、メッセージが拒否された場合、修復段階にメッセージが送信されます。 修理会社または作成者の段階、Message Repair でメッセージが拒否された場合は New Submission Message Repair and New Submission のオーケストレーション インスタンスにメッセージを拒否済としてマークする特定のプロパティを持つメッセージを送信します。  
  
 このセクションでは、Message Repair and New Submission のロールに対して定義されている機能に基づくデジタル署名を処理する方法について説明します。 役割と機能の組み合わせ、ワークフローで「ステージング」と呼びます。  
  
> [!NOTE]
>  ロールの「作成」は、すべての部門間で 1 つの作成者に制限されます。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [作成およびステージの修復](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [キー更新の検証ステージ](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [承認ステージ](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [デジタル証明書の配布](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)