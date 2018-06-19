---
title: UninstallApp コマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286786"
---
# <a name="uninstallapp-command"></a><span data-ttu-id="3c35b-102">UninstallApp コマンド</span><span class="sxs-lookup"><span data-stu-id="3c35b-102">UninstallApp Command</span></span>
<span data-ttu-id="3c35b-103">BizTalk アプリケーションをローカル コンピューターからアンインストールし、さらに、コントロール パネルの [プログラムの追加と削除] に表示されるプログラム一覧からも削除します。</span><span class="sxs-lookup"><span data-stu-id="3c35b-103">Uninstalls a BizTalk application from the local computer and also removes the application from the list of programs in Add or Remove Programs in Control Panel.</span></span> <span data-ttu-id="3c35b-104">このコマンドの実行結果は、[プログラムの追加と削除] を使ってアプリケーションを削除した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="3c35b-104">This command has the same effect as removing an application by using Add or Remove Programs.</span></span> <span data-ttu-id="3c35b-105">このアプリケーションに対して複数の .msi ファイルがインストールされている場合、これらの .msi ファイルによってインストールされたアイテムがすべてアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3c35b-105">If multiple .msi files have been installed for this application, all of the items installed by all of the .msi files are uninstalled.</span></span>  
  
 <span data-ttu-id="3c35b-106">このコマンドでは、[プログラムの追加と削除] に表示されるアプリケーション名と同じアプリケーション名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c35b-106">The application name that you specify for this command must match the name of the application as displayed in Add or Remove Programs.</span></span> <span data-ttu-id="3c35b-107">使用することができます、アプリケーション名のことを確認していない場合は、 **ListPackage** 」の説明に従って、取得するコマンド[ListPackage コマンド](../core/listpackage-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c35b-107">If you are unsure of the application name, you can use the **ListPackage** command to obtain it, as described in [ListPackage Command](../core/listpackage-command.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c35b-108">.msi ファイルをダブルクリックしてアプリケーションをアンインストールすることもできますが、この方法はサポートの対象外となります。</span><span class="sxs-lookup"><span data-stu-id="3c35b-108">Although it is possible to uninstall an application by double-clicking the .msi file, doing this is not supported.</span></span> <span data-ttu-id="3c35b-109">同じアプリケーションに対して複数の .msi ファイルがインストールされていた場合、この方法では、アプリケーションに関連付けられているアイテムを完全にアンインストールすることはできないためです。</span><span class="sxs-lookup"><span data-stu-id="3c35b-109">This is because multiple .msi files can be installed for the same application, and using this method will not uninstall all of the items associated with the application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="3c35b-110">使用方法</span><span class="sxs-lookup"><span data-stu-id="3c35b-110">Usage</span></span>  
 <span data-ttu-id="3c35b-111">**BTSTask UninstallApp/applicationname は:** *値*</span><span class="sxs-lookup"><span data-stu-id="3c35b-111">**BTSTask UninstallApp /ApplicationName:** *value*</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="3c35b-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c35b-112">Parameters</span></span>  
  
|<span data-ttu-id="3c35b-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c35b-113">Parameter</span></span>|<span data-ttu-id="3c35b-114">必須</span><span class="sxs-lookup"><span data-stu-id="3c35b-114">Required</span></span>|<span data-ttu-id="3c35b-115">Description</span><span class="sxs-lookup"><span data-stu-id="3c35b-115">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="3c35b-116">**/ApplicationName** (または **/A**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3c35b-116">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="3c35b-117">はい</span><span class="sxs-lookup"><span data-stu-id="3c35b-117">Yes</span></span>|<span data-ttu-id="3c35b-118">アンインストールする BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="3c35b-118">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="3c35b-119">名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c35b-119">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="3c35b-120">サンプル</span><span class="sxs-lookup"><span data-stu-id="3c35b-120">Sample</span></span>  
 <span data-ttu-id="3c35b-121">**Applicationname: myapplication BTSTask UninstallApp**</span><span class="sxs-lookup"><span data-stu-id="3c35b-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c35b-122">解説</span><span class="sxs-lookup"><span data-stu-id="3c35b-122">Remarks</span></span>  
 <span data-ttu-id="3c35b-123">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="3c35b-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="3c35b-124">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="3c35b-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c35b-125">参照</span><span class="sxs-lookup"><span data-stu-id="3c35b-125">See Also</span></span>  
 <span data-ttu-id="3c35b-126">[BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3c35b-126">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="3c35b-127">BizTalk アプリケーションをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3c35b-127">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)