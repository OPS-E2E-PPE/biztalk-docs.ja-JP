---
title: "失敗したメッセージおよび元のオブジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65598ef44bfe3e34bd1695aa81bee368c5175793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="failed-messages-and-errorcollection-objects"></a>失敗したメッセージと元のオブジェクト
昇格させたプロパティは、失敗したメッセージを修飾することだけでなく[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 、失敗したメッセージをメッセージと共に、メッセージ ボックス データベースに公開*一部*という**ErrorSegment**. このエラーの部分を含む XML を表す、**元**オブジェクト。 A4SWIFT 逆アセンブラーは追加、**元**メッセージ (解析、XML の検証、およびビジネス ルール エンジン (BRE)) を処理の各段階のオブジェクト。  
  
 **元**オブジェクトは、コレクションの*エラー オブジェクト*を表す特定のエラーまたはエラー メッセージの処理中にします。 個々 のエラー オブジェクトには、(メッセージとエラーの説明内の場所) などの 1 つのエラーの詳細が含まれます。  
  
 詳細については、**元**アプリケーション プログラミング インターフェイス (API) と使用方法の詳細は、元のクラスを参照してください。 個々 のエラー オブジェクトに関する詳細については、ErrorBase クラス (エラー オブジェクトの基本クラス)、BreValidationError クラス、ParseError クラス、および XmlValidationError クラスを参照してください。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [キャプチャおよび Message Repair ソリューションを拡張します。](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)