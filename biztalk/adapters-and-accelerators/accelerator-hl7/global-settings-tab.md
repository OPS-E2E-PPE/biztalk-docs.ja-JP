---
title: グローバル設定 タブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a883a4d506d3ee65a5ef0edc7ab5dc6495f039
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267980"
---
# <a name="global-settings-tab"></a>グローバル設定 タブ
使用する、**グローバル設定** タブで使用されるログ ストアを構成する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。  

 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスの 、**グローバル設定** タブで、次の操作を行います。  


|     プロパティ      |                                                                                                                                                目的                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **WMI**      |                                                                 生成する場合は、このオプションを選択[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 の Management Instrumentation (WMI) 通知します。                                                                  |
|      **SQL**      | Microsoft を使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]BTAHL7 のログ記録ストアとして。 **注:** BTAHL7 では、存在しない場合は、ログに必要なテーブルが自動的に作成されます。 |
|  **SQL Server**   |            型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、64 文字です。<br /><br /> 既定のサーバーとデータベース名は、構成されている BTAHL7 データベースです。            |
| **データベース名** |                                                 型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は 128 文字です。                                                 |
|   **イベント ログ**   |                使用する場合は、このオプションを選択、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] BTAHL7 のログ記録ストアとしてのイベント ログ。 使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーでイベント メッセージを表示します。                 |

