---
title: メッセージと ErrorCollection オブジェクトが失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c925cecaec71eb0be8f9dd3d997b33090f286f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377856"
---
# <a name="failed-messages-and-errorcollection-objects"></a>失敗したメッセージと ErrorCollection オブジェクト
Microsoft の昇格させたプロパティを持つ失敗したメッセージを修飾することだけでなく[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]追加のメッセージをメッセージ ボックス データベースに、失敗したメッセージを発行*一部*という**ErrorSegment**. このエラーの部分を含む XML を表す、 **ErrorCollection**オブジェクト。 A4SWIFT の逆アセンブラーが表示されます、 **ErrorCollection**メッセージ処理 (解析、XML の検証とビジネス ルール エンジン (BRE) の検証) の各段階中のオブジェクト。  
  
 **ErrorCollection**オブジェクトのコレクションである*エラー オブジェクト*、メッセージ処理中に特定のエラーまたは失敗を表す各します。 個々 のエラー オブジェクトには、(メッセージとエラーの説明の場所) などの 1 つのエラーの詳細が含まれます。  
  
 詳細については、 **ErrorCollection**アプリケーション プログラミング インターフェイス (API) と使用方法の詳細は、元のクラスを参照してください。 個々 のエラー オブジェクトの詳細については、ErrorBase クラス (エラー オブジェクトの基本クラス)、BreValidationError クラス、ParseError クラス、および XmlValidationError クラスを参照してください。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [キャプチャおよびメッセージ修復のソリューションの機能拡張](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)