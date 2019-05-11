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
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a><span data-ttu-id="1399f-102">MQSeries アダプター用コマンドライン構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="1399f-102">Command-Line Configuration Wizard for the MQSeries Adapter</span></span>
<span data-ttu-id="1399f-103">ウィザードでは、インストール、アンインストール、およびアクションのログ記録の 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1399f-103">The wizard has four options for installing, uninstalling, and logging actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1399f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1399f-104">Syntax</span></span>  
 <span data-ttu-id="1399f-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span><span class="sxs-lookup"><span data-stu-id="1399f-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span></span>  
  
|<span data-ttu-id="1399f-106">オプション</span><span class="sxs-lookup"><span data-stu-id="1399f-106">Option</span></span>|<span data-ttu-id="1399f-107">説明</span><span class="sxs-lookup"><span data-stu-id="1399f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1399f-108">**/u**</span><span class="sxs-lookup"><span data-stu-id="1399f-108">**/u**</span></span>|<span data-ttu-id="1399f-109">MQSAgent をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1399f-109">Uninstalls the MQSAgent.</span></span>|  
|<span data-ttu-id="1399f-110">**/i** *config.xml*</span><span class="sxs-lookup"><span data-stu-id="1399f-110">**/i** *config.xml*</span></span>|<span data-ttu-id="1399f-111">ファイルの情報を使用して、MQSAgent がインストール*config.xml*します。</span><span class="sxs-lookup"><span data-stu-id="1399f-111">Installs the MQSAgent using the information in the file *config.xml*.</span></span>|  
|<span data-ttu-id="1399f-112">**/l** *logfile*</span><span class="sxs-lookup"><span data-stu-id="1399f-112">**/l** *logfile*</span></span>|<span data-ttu-id="1399f-113">操作がファイルにログ記録*logfile*します。</span><span class="sxs-lookup"><span data-stu-id="1399f-113">Logs actions to the file *logfile*.</span></span>|  
|<span data-ttu-id="1399f-114">**/?**</span><span class="sxs-lookup"><span data-stu-id="1399f-114">**/?**</span></span>|<span data-ttu-id="1399f-115">コマンド ライン オプションを説明するダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-115">Displays a dialog box describing the command-line options.</span></span>|  
  
 <span data-ttu-id="1399f-116">構成情報を含む XML ファイルの内容は、使用している Windows のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1399f-116">The contents of the XML file that contains the configuration information may vary, depending on the version of Windows you are using.</span></span> <span data-ttu-id="1399f-117">構成ファイルの形式の詳細については、次を参照してください。 [MQSeries アダプターの構成ファイルを XML](../core/xml-configuration-file-for-the-mqseries-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="1399f-117">For more information about the configuration file format, see [XML Configuration File for the MQSeries Adapter](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1399f-118">アダプターでは、構成ウィザードの実行中には機能しません。</span><span class="sxs-lookup"><span data-stu-id="1399f-118">The adapter does not work while the configuration wizard is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1399f-119">コマンドライン構成ウィザードを使用して、MQSAgent を再構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1399f-119">You cannot reconfigure MQSAgent with the command-line configuration wizard.</span></span> <span data-ttu-id="1399f-120">エージェントをアンインストール ウィザードを初めて実行する必要があります (**/u**)、し構成する際に実行 (**/i**)。</span><span class="sxs-lookup"><span data-stu-id="1399f-120">You must first run the wizard to uninstall the agent (**/u**), and then run it to configure (**/i**).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1399f-121">参照</span><span class="sxs-lookup"><span data-stu-id="1399f-121">See Also</span></span>  
 [<span data-ttu-id="1399f-122">MQSeries アダプターのサイレント構成</span><span class="sxs-lookup"><span data-stu-id="1399f-122">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)