---
title: "A4SWIFT データベースのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cd2cd1eadf3dc6f11a6e3178258caaaf88006d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-the-a4swift-database"></a>A4SWIFT データベースをバックアップします。
日常的に、致命的な障害のリスクを低減するため、BizTalk Server および A4SWIFT のシステムのデータベースをバックアップしてください。 BizTalk Server ソース システム、および A4SWIFT データベースにこれらのデータベースがあります。 に加えて、リスクを低減するには、これはすることもできます大きなサイズに拡大できる A4SWIFT 履歴ファイルを削除します。  
  
 BizTalk Server ソース システム内のデータベースのバックアップの詳細についてを参照してください「および復元する BizTalk Server データベースのバックアップ」で、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。 このトピックでは、BizTalk データベースのバックアップを使用する BizTalk Server のバックアップ ジョブについて説明します。  
  
 A4SWIFT データベースのバックアップの詳細については、トピックでは、「方法に戻るをカスタム データベース」を参照してください。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。 このトピックでは、カスタムの A4SWIFT データベースを含めるに BizTalk Server のバックアップ ジョブを変更する方法について説明します。