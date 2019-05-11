---
title: UninstallApp コマンド |Microsoft Docs
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
ms.openlocfilehash: b4fc9da4d645b710490447addc2d4fd8691f199d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292686"
---
# <a name="uninstallapp-command"></a><span data-ttu-id="d1136-102">UninstallApp コマンド</span><span class="sxs-lookup"><span data-stu-id="d1136-102">UninstallApp Command</span></span>
<span data-ttu-id="d1136-103">ローカル コンピューターから BizTalk アプリケーションをアンインストールし、アプリケーションを追加でプログラムまたはコントロール パネルの [プログラムの削除] の一覧からも削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1136-103">Uninstalls a BizTalk application from the local computer and also removes the application from the list of programs in Add or Remove Programs in Control Panel.</span></span> <span data-ttu-id="d1136-104">このコマンドでは、追加または削除するプログラムを使用してアプリケーションを削除すると同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="d1136-104">This command has the same effect as removing an application by using Add or Remove Programs.</span></span> <span data-ttu-id="d1136-105">複数の .msi ファイルは、このアプリケーションのインストールされている、すべてのすべての .msi ファイルによってインストールされている項目はアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1136-105">If multiple .msi files have been installed for this application, all of the items installed by all of the .msi files are uninstalled.</span></span>  
  
 <span data-ttu-id="d1136-106">追加と削除 に表示される、このコマンドの指定したアプリケーション名は、アプリケーションの名前に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1136-106">The application name that you specify for this command must match the name of the application as displayed in Add or Remove Programs.</span></span> <span data-ttu-id="d1136-107">アプリケーション名の確信できない場合は使用できます、 **ListPackage** 」の説明に従って、取得するコマンドを[ListPackage コマンド](../core/listpackage-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1136-107">If you are unsure of the application name, you can use the **ListPackage** command to obtain it, as described in [ListPackage Command](../core/listpackage-command.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d1136-108">.Msi ファイルをダブルクリックしてアプリケーションをアンインストールすることはできますが、これはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1136-108">Although it is possible to uninstall an application by double-clicking the .msi file, doing this is not supported.</span></span> <span data-ttu-id="d1136-109">これは、同じアプリケーションの複数の .msi ファイルをインストールすることができます、このメソッドを使用してはアンインストールされませんすべてのアプリケーションに関連付けられている項目のためです。</span><span class="sxs-lookup"><span data-stu-id="d1136-109">This is because multiple .msi files can be installed for the same application, and using this method will not uninstall all of the items associated with the application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="d1136-110">使用方法</span><span class="sxs-lookup"><span data-stu-id="d1136-110">Usage</span></span>  
 <span data-ttu-id="d1136-111">**BTSTask UninstallApp/applicationname は:** *値*</span><span class="sxs-lookup"><span data-stu-id="d1136-111">**BTSTask UninstallApp /ApplicationName:** *value*</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="d1136-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1136-112">Parameters</span></span>  
  
|<span data-ttu-id="d1136-113">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1136-113">Parameter</span></span>|<span data-ttu-id="d1136-114">必須</span><span class="sxs-lookup"><span data-stu-id="d1136-114">Required</span></span>|<span data-ttu-id="d1136-115">説明</span><span class="sxs-lookup"><span data-stu-id="d1136-115">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="d1136-116">**/ApplicationName** (または **/A**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="d1136-116">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="d1136-117">はい</span><span class="sxs-lookup"><span data-stu-id="d1136-117">Yes</span></span>|<span data-ttu-id="d1136-118">アンインストールする BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="d1136-118">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="d1136-119">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1136-119">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="d1136-120">サンプル</span><span class="sxs-lookup"><span data-stu-id="d1136-120">Sample</span></span>  
 <span data-ttu-id="d1136-121">**BTSTask UninstallApp applicationname:**</span><span class="sxs-lookup"><span data-stu-id="d1136-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1136-122">コメント</span><span class="sxs-lookup"><span data-stu-id="d1136-122">Remarks</span></span>  
 <span data-ttu-id="d1136-123">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="d1136-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="d1136-124">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="d1136-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1136-125">参照</span><span class="sxs-lookup"><span data-stu-id="d1136-125">See Also</span></span>  
 <span data-ttu-id="d1136-126">[BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d1136-126">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="d1136-127">BizTalk アプリケーションをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="d1136-127">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)