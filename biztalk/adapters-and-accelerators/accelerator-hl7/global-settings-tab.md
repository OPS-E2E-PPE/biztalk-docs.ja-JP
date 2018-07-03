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
ms.openlocfilehash: 5c19cfb387ba3cce61d21c467c1c91674204d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998683"
---
# <a name="global-settings-tab"></a>グローバル設定 タブ
使用する、**グローバル設定** タブで使用されるログ ストアを構成する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。  

 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスの 、**グローバル設定** タブで、次の操作を行います。  


|     プロパティ      |                                                                                                                                                目的                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **WMI**      |                                                                 生成する場合は、このオプションを選択[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 の Management Instrumentation (WMI) 通知します。                                                                  |
|      **SQL**      | Microsoft を使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]BTAHL7 のログ記録ストアとして。 **注:** BTAHL7 が存在しない場合は、ログに必要なテーブルを自動的に作成されます。 |
|  **SQL Server**   |            型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、64 文字です。<br /><br /> 既定のサーバーとデータベース名は、構成されている BTAHL7 データベースです。            |
| **データベース名** |                                                 型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は 128 文字です。                                                 |
|   **イベント ログ**   |                使用する場合は、このオプションを選択、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] BTAHL7 のログ記録ストアとしてのイベント ログ。 使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーでイベント メッセージを表示します。                 |

