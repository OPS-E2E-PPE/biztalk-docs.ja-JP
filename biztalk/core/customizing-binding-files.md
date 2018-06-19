---
title: バインド ファイルをカスタマイズする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1534be96255084b963ed3883a1370af00f73b605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238370"
---
# <a name="customizing-binding-files"></a><span data-ttu-id="16fd1-102">バインド ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="16fd1-102">Customizing Binding Files</span></span>
<span data-ttu-id="16fd1-103">バインド ファイルは、BizTalk 管理データベース内のアイテム、およびこれらのアイテム間のリレーションシップを記述する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="16fd1-103">Binding files are XML files that describe artifacts in a BizTalk Management database and the relationship between these artifacts.</span></span> <span data-ttu-id="16fd1-104">バインド ファイルは、1 つの BizTalk 構成データベースから構成情報をエクスポートし、この情報を別の BizTalk 構成データベースにインポートする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16fd1-104">Binding files are useful for exporting configuration information from one BizTalk configuration database and importing this information into another BizTalk configuration database.</span></span> <span data-ttu-id="16fd1-105">たとえば、開発者は BizTalk ソリューションとその関連アイテムを開発環境でデザインし、これらのアイテムをバインド ファイルにエクスポートして、最後にこれらのアイテムを実稼動環境にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="16fd1-105">For example, a developer may design a BizTalk solution and its related artifacts in a development environment, then export these artifacts to a binding file and finally, import these artifacts into a production environment.</span></span> <span data-ttu-id="16fd1-106">また、バインド ファイルを使用して、既存の構成を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="16fd1-106">You can also use a binding file to update an existing configuration.</span></span> <span data-ttu-id="16fd1-107">たとえば、開発環境内の構成の変更を、バインド ファイルを使用して実稼動環境に適用できます。</span><span class="sxs-lookup"><span data-stu-id="16fd1-107">For example you can apply configuration changes made in a development environment to your production environment with a binding file.</span></span> <span data-ttu-id="16fd1-108">このトピックでは、既存の構成をバインド ファイルで更新する際の考慮事項、バインド ファイルの構造、およびバインド ファイルで設定できるアダプター固有の構成プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16fd1-108">This topic discusses considerations when updating an existing configuration with a binding file, the structure of a binding file, and adapter specific configuration properties that can be set in a binding file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16fd1-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="16fd1-109">In This Section</span></span>  
  
-   [<span data-ttu-id="16fd1-110">バインド ファイルと共に、既存の構成を更新</span><span class="sxs-lookup"><span data-stu-id="16fd1-110">Updating an Existing Configuration with a Binding File</span></span>](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [<span data-ttu-id="16fd1-111">バインド ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="16fd1-111">Structure of a Binding File</span></span>](../core/structure-of-a-binding-file.md)  
  
-   [<span data-ttu-id="16fd1-112">統合 BizTalk アダプターの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="16fd1-112">Configuration Properties for Integrated BizTalk Adapters</span></span>](../core/configuration-properties-for-integrated-biztalk-adapters.md)