---
title: ログ ストアの選択 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4814cda3568d724664bd98556d46e5ae3552683c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289183"
---
# <a name="selecting-the-logging-store"></a>ログ ストアの選択
Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]など、さまざまなログ記録ストアの組み合わせを選択するオプションの[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI)、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]、および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ログ。  

 使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ログ ストアを構成するエクスプ ローラーを構成します。  

 次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーとなるログ ストアを選択します。  

### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  

-   をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator for HL7**、 をクリックし、 **BTAHL7 構成エクスプ ローラー**します。  

### <a name="to-select-the--logging-store"></a>ログ ストアを選択するには  

1. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、**グローバル設定** タブで、次の操作します。  


   |     プロパティ      |                                                                                                                                     目的                                                                                                                                     |
   |-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      **WMI**      |                                                                                                      BTAHL7 の WMI 通知を生成する場合は、このオプションを選択します。                                                                                                      |
   |      **SQL**      |                     使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ストアとして。 **注:** BTAHL7 では、存在しない場合は、ログに必要なテーブルが自動的に作成されます。                     |
   |  **SQL Server**   | 型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は、64 文字です。<br /><br /> 既定のサーバーとデータベース名は、構成されている BTAHL7 データベースです。 |
   | **データベース名** |                                      型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。 これは、選択したときに必要な**SQL**オプション。 許容最大長は 128 文字です。                                      |
   |  **イベント ログ**   |          使用する場合は、このオプションを選択、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ログ ストアとしてのイベント ログ。 使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーでイベント メッセージを表示します。          |


2. **[保存]** をクリックします。  

   > [!NOTE]
   >  ログ記録イベント ブローカーによって記録されたイベントのロケールは、ログ記録のサービス アカウントのロケールに依存します。  
   > 
   > [!NOTE]
   >  Microsoft ではパスワードを変更するログ記録のサービス アカウントのパスワードを変更するときに最初にする必要があります[!INCLUDE[btsAD](../../includes/btsad-md.md)]ディレクトリ サービス、および実行するすべてのサーバーでログ記録サービスのパスワードを変更した後、ログ記録がサービスを再起動します。  

## <a name="see-also"></a>参照  
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [ログ記録の構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)