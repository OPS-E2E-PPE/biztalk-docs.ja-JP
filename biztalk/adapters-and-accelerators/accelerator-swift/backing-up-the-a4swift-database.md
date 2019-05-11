---
title: A4SWIFT データベースのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e69325509131c6ea1674c3f6c3b6153f3ea2f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378660"
---
# <a name="backing-up-the-a4swift-database"></a>A4SWIFT データベースをバックアップします。
致命的な障害のリスクを軽減する BizTalk Server と A4SWIFT システムは、データベースを定期的にバックアップする必要があります。 これらのデータベースには、BizTalk Server ソース システム、および A4SWIFT データベースが含まれます。 リスクを削減だけでなく大きなサイズに拡大できる A4SWIFT 履歴ファイルを削除することを実現これはもします。  
  
 BizTalk Server ソース システムで、データベースのバックアップの詳細については、BizTalk Server ヘルプで「し、復元する BizTalk Server データベースのバックアップ」を参照してください。 このトピックでは、BizTalk データベースをバックアップするために使用する BizTalk Server のバックアップ ジョブについて説明します。  
  
 A4SWIFT データベースをバックアップする方法の詳細については、BizTalk Server ヘルプの「方法に戻るをカスタム データベース」を参照してください。 このトピックでは、カスタムの A4SWIFT データベースを含めるに BizTalk Server のバックアップ ジョブを変更する方法について説明します。