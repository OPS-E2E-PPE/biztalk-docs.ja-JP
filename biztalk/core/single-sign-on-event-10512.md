---
title: 'シングル サインオン: イベント 10512 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54ba5a340a1a7590dae72016a3e747726ea68125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980963"
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="1ae2b-102">シングル サインオン: イベント 10512</span><span class="sxs-lookup"><span data-stu-id="1ae2b-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="1ae2b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1ae2b-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1ae2b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1ae2b-104">Product Name</span></span>   |                 <span data-ttu-id="1ae2b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1ae2b-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1ae2b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1ae2b-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1ae2b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1ae2b-107">Event ID</span></span>     |                           <span data-ttu-id="1ae2b-108">10512</span><span class="sxs-lookup"><span data-stu-id="1ae2b-108">10512</span></span>                            |
|  <span data-ttu-id="1ae2b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1ae2b-109">Event Source</span></span>   |                           <span data-ttu-id="1ae2b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1ae2b-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1ae2b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1ae2b-111">Component</span></span>    |                            <span data-ttu-id="1ae2b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1ae2b-112">N\A</span></span>                             |
|  <span data-ttu-id="1ae2b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1ae2b-113">Symbolic Name</span></span>  |                   <span data-ttu-id="1ae2b-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="1ae2b-114">SSO_ERROR_LOADLIBRARY</span></span>                    |
|  <span data-ttu-id="1ae2b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1ae2b-115">Message Text</span></span>   |      <span data-ttu-id="1ae2b-116">%1 を読み込めませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="1ae2b-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="1ae2b-117">エラー コード: %2。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-117">Error code: %2.</span></span>       |

## <a name="explanation"></a><span data-ttu-id="1ae2b-118">説明</span><span class="sxs-lookup"><span data-stu-id="1ae2b-118">Explanation</span></span>  
 <span data-ttu-id="1ae2b-119">このエラー イベントは、指定されたダイナミック リンク ライブラリ (DLL) を SSO サーバー プロセスに読み込めなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="1ae2b-120">DLL が SSO インストール ディレクトリ (通常、C:\Program Files\Common Files\Enterprise Single Sign-On) に存在しない場合、セットアップが正常に完了していないか、セットアップ完了後に DLL が削除されたを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="1ae2b-121">DLL が存在する場合は、SSO サービスで DLL への適切なパスを解決できないという問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="1ae2b-122">さらに、DLL 自体が壊れている可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-122">Additionally, the DLL itself could be corrupted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1ae2b-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1ae2b-123">User Action</span></span>  
 <span data-ttu-id="1ae2b-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="1ae2b-125">広い範囲でセットアップの失敗が疑われる場合は、製品のアンインストールと再インストールが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  

- <span data-ttu-id="1ae2b-126">1 つの DLL が不足または破損している場合は、DLL の置き換えを試みてからサービスを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="1ae2b-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="1ae2b-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="1ae2b-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="1ae2b-128">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="1ae2b-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
