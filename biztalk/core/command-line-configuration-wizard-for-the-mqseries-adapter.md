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
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a><span data-ttu-id="76526-102">MQSeries アダプタ用コマンドライン構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="76526-102">Command-Line Configuration Wizard for the MQSeries Adapter</span></span>
<span data-ttu-id="76526-103">このウィザードには、インストール、アンインストール、アクションのログ記録に関する 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="76526-103">The wizard has four options for installing, uninstalling, and logging actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76526-104">構文</span><span class="sxs-lookup"><span data-stu-id="76526-104">Syntax</span></span>  
 <span data-ttu-id="76526-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span><span class="sxs-lookup"><span data-stu-id="76526-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span></span>  
  
|<span data-ttu-id="76526-106">オプション</span><span class="sxs-lookup"><span data-stu-id="76526-106">Option</span></span>|<span data-ttu-id="76526-107">Description</span><span class="sxs-lookup"><span data-stu-id="76526-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="76526-108">**/u**</span><span class="sxs-lookup"><span data-stu-id="76526-108">**/u**</span></span>|<span data-ttu-id="76526-109">MQSAgent をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="76526-109">Uninstalls the MQSAgent.</span></span>|  
|<span data-ttu-id="76526-110">**/i** *config.xml*</span><span class="sxs-lookup"><span data-stu-id="76526-110">**/i** *config.xml*</span></span>|<span data-ttu-id="76526-111">ファイルの情報を使用して、MQSAgent がインストール*config.xml*です。</span><span class="sxs-lookup"><span data-stu-id="76526-111">Installs the MQSAgent using the information in the file *config.xml*.</span></span>|  
|<span data-ttu-id="76526-112">**/l** *ログ ファイル*</span><span class="sxs-lookup"><span data-stu-id="76526-112">**/l** *logfile*</span></span>|<span data-ttu-id="76526-113">ファイルに操作を記録*logfile*です。</span><span class="sxs-lookup"><span data-stu-id="76526-113">Logs actions to the file *logfile*.</span></span>|  
|<span data-ttu-id="76526-114">**/?**</span><span class="sxs-lookup"><span data-stu-id="76526-114">**/?**</span></span>|<span data-ttu-id="76526-115">コマンド ライン オプションを説明するダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="76526-115">Displays a dialog box describing the command-line options.</span></span>|  
  
 <span data-ttu-id="76526-116">構成情報が含まれている XML ファイルの内容は、使用している Windows のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76526-116">The contents of the XML file that contains the configuration information may vary, depending on the version of Windows you are using.</span></span> <span data-ttu-id="76526-117">構成ファイルの形式の詳細については、次を参照してください。 [、MQSeries アダプターの構成ファイルを XML](../core/xml-configuration-file-for-the-mqseries-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="76526-117">For more information about the configuration file format, see [XML Configuration File for the MQSeries Adapter](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="76526-118">アダプタは構成ウィザードの実行中は動作しません。</span><span class="sxs-lookup"><span data-stu-id="76526-118">The adapter does not work while the configuration wizard is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76526-119">コマンド ライン構成ウィザードを使用して MQSAgent を再構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="76526-119">You cannot reconfigure MQSAgent with the command-line configuration wizard.</span></span> <span data-ttu-id="76526-120">まず、エージェントをアンインストール ウィザードを実行する必要があります (**/u**)、構成を実行し (**/i**)。</span><span class="sxs-lookup"><span data-stu-id="76526-120">You must first run the wizard to uninstall the agent (**/u**), and then run it to configure (**/i**).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76526-121">参照</span><span class="sxs-lookup"><span data-stu-id="76526-121">See Also</span></span>  
 [<span data-ttu-id="76526-122">MQSeries アダプタのサイレント構成</span><span class="sxs-lookup"><span data-stu-id="76526-122">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)