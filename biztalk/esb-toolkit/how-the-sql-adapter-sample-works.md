---
title: SQL アダプター サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e59df235628539786917d7aa483e23a18d7c87c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279068"
---
# <a name="how-the-sql-adapter-sample-works"></a>SQL アダプター サンプルのしくみ
SQL Adapter サンプルは、ルーティング サービスとトランス フォームのメッセージング サービスで構成されているサンプルの双方向旅程を提供します。  
  
 ルーティングのサービスを構成するには、静的なリゾルバーは、という名前の WCF カスタム アダプターのプロバイダーを使用して InsertProduct GlobalBankESB データベース内の SQL ストアド プロシージャを実行するメッセージをルーティングする必要がありますを指定します。  
  
 変換サービスでは、受信メッセージを InsertProduct ストアド プロシージャによって受け入れられる形式に変換するマップを指定します。