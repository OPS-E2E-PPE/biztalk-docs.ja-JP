---
title: MQSeries アダプター用コマンドライン構成ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174e40f413be4ae3fab89965b842dee8fb8ba513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357714"
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a>MQSeries アダプター用コマンドライン構成ウィザード
ウィザードでは、インストール、アンインストール、およびアクションのログ記録の 4 つのオプションがあります。  
  
## <a name="syntax"></a>構文  
 **mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**  
  
|オプション|説明|  
|------------|-----------------|  
|**/u**|MQSAgent をアンインストールします。|  
|**/i** *config.xml*|ファイルの情報を使用して、MQSAgent がインストール*config.xml*します。|  
|**/l** *logfile*|操作がファイルにログ記録*logfile*します。|  
|**/?**|コマンド ライン オプションを説明するダイアログ ボックスが表示されます。|  
  
 構成情報を含む XML ファイルの内容は、使用している Windows のバージョンによって異なる場合があります。 構成ファイルの形式の詳細については、次を参照してください。 [MQSeries アダプターの構成ファイルを XML](../core/xml-configuration-file-for-the-mqseries-adapter.md)します。  
  
> [!IMPORTANT]
>  アダプターでは、構成ウィザードの実行中には機能しません。  
  
> [!NOTE]
>  コマンドライン構成ウィザードを使用して、MQSAgent を再構成することはできません。 エージェントをアンインストール ウィザードを初めて実行する必要があります (**/u**)、し構成する際に実行 (**/i**)。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのサイレント構成](../core/silent-configuration-of-the-mqseries-adapter.md)