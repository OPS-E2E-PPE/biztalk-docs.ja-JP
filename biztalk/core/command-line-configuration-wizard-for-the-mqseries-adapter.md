---
title: MQSeries アダプタ用コマンドライン構成ウィザード |Microsoft ドキュメント
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
ms.openlocfilehash: ee73b890fca43a3651f22092486e5898862b0b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232058"
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a>MQSeries アダプタ用コマンドライン構成ウィザード
このウィザードには、インストール、アンインストール、アクションのログ記録に関する 4 つのオプションがあります。  
  
## <a name="syntax"></a>構文  
 **mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**  
  
|オプション|Description|  
|------------|-----------------|  
|**/u**|MQSAgent をアンインストールします。|  
|**/i** *config.xml*|ファイルの情報を使用して、MQSAgent がインストール*config.xml*です。|  
|**/l** *ログ ファイル*|ファイルに操作を記録*logfile*です。|  
|**/?**|コマンド ライン オプションを説明するダイアログ ボックスを表示します。|  
  
 構成情報が含まれている XML ファイルの内容は、使用している Windows のバージョンによって異なる場合があります。 構成ファイルの形式の詳細については、次を参照してください。 [、MQSeries アダプターの構成ファイルを XML](../core/xml-configuration-file-for-the-mqseries-adapter.md)です。  
  
> [!IMPORTANT]
>  アダプタは構成ウィザードの実行中は動作しません。  
  
> [!NOTE]
>  コマンド ライン構成ウィザードを使用して MQSAgent を再構成することはできません。 まず、エージェントをアンインストール ウィザードを実行する必要があります (**/u**)、構成を実行し (**/i**)。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタのサイレント構成](../core/silent-configuration-of-the-mqseries-adapter.md)