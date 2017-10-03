---
title: "InfoPath セキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ec5478af7c404840bf1c5c80be5520e405bd26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="infopath-security"></a>InfoPath のセキュリティ
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 では、XML 署名を使用して、デジタル証明書を使用してフォームにデジタル署名できます。 XML 署名では、XML ドキュメントに含まれるデータを保護するために使用する XML ベースのデジタル署名用の標準を定義します。 XML 署名は、World Wide Web Consortium (W3C) によって管理される標準です。  
  
 デジタル署名は、マクロまたはドキュメントの認証の電子、暗号化ベース、セキュリティで保護されたタイムスタンプです。 デジタル署名するときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、フォームを使用して入力 XML インスタンスが「スタンプ」デジタル署名 (署名公開キーおよび署名されたデータ ダイジェストは、XML に専用のノードに書き込まれます)。 この署名は、XML ドキュメントが署名者から発信されが改変されていないことを確認します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]署名の検証可能な否認、部分署名、cosigning と副強化されたデジタル署名のサポートを提供します。  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT によって提供される FormGenerator ユーティリティを使用して生成されたフォームでは、デジタル署名の countersigning メソッドを使用して、互いの上に重ねられます countersigners の署名を使用できます。 この countersigning 署名スタックの作成、SWIFT メッセージを編集または確認し、1 つ以上のレビュー担当者と、承認者によって承認されたメッセージが含まれる、および最後に、ワークフロー内のすべての段階の後にそのメッセージを送信する、人間指向プロセスをモデル化します。サインオフします。  
  
 Repairers、レビュー担当者、または承認者は、承認または拒否するかどうかに関係なくメッセージに署名します。 署名は、応答の信頼性を示すし、「承認済み」の意思決定を必ずしも意味しません。  
  
 ときに、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームが送信されるメッセージの有効性がチェックされ、フォームへの署名、ユーザーが適切なロールにあります。  
  
 (修復) だけでなく、ワークフローで何らかの段階でメッセージが拒否された場合、メッセージは、修復ステージに送信されます。 場合は、修理会社または作成者段階で、Message Repair、メッセージは拒否され、New Submission Message Repair and New Submission のオーケストレーション インスタンスにスイッチ_バック拒否メッセージをマークする特定のプロパティを持つメッセージを送信します。  
  
 このセクションでは、Message Repair and New Submission のロールに対して定義されている機能に基づくデジタル署名を処理する方法について説明します。 役割と機能の組み合わせには、ワークフロー内の「ステージ」は呼び出されます。  
  
> [!NOTE]
>  ロールの「作成」は、すべての部門間で 1 つの作成者に制限されます。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [作成し、修復ステージ](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [検証ステージを鍵更新します。](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [承認ステージ](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [デジタル証明書を配布します。](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)