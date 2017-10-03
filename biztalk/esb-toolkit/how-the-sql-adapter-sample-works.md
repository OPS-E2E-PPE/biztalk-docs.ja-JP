---
title: "SQL アダプタのサンプルのしくみ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ff56f2f2f88d35290ffd897d107910e206ac98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-sql-adapter-sample-works"></a>SQL アダプタのサンプルのしくみ
SQL Adapter サンプルは、ルーティング サービスとトランス フォームのメッセージング サービスで構成されているサンプルの双方向旅程を提供します。  
  
 ルーティングのサービスを構成するには、静的なリゾルバーは、Wcf-custom アダプター プロバイダーを使用して InsertProduct をという名前の GlobalBankESB データベース内で SQL ストアド プロシージャを実行する、メッセージをルーティングする必要がありますを指定します。  
  
 変換サービスでは、受信メッセージを InsertProduct ストアド プロシージャによって受け入れられる形式に変換するマップを指定します。