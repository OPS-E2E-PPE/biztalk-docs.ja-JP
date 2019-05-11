---
title: シングル サインオン:イベント 10512 |Microsoft Docs
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
ms.openlocfilehash: bf29293c12a566a82835510e07f23e52ba0ba243
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243393"
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="3d922-102">シングル サインオン:イベント 10512</span><span class="sxs-lookup"><span data-stu-id="3d922-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="3d922-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3d922-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="3d922-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3d922-104">Product Name</span></span>   |                 <span data-ttu-id="3d922-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3d922-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="3d922-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3d922-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="3d922-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3d922-107">Event ID</span></span>     |                           <span data-ttu-id="3d922-108">10512</span><span class="sxs-lookup"><span data-stu-id="3d922-108">10512</span></span>                            |
|  <span data-ttu-id="3d922-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3d922-109">Event Source</span></span>   |                           <span data-ttu-id="3d922-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3d922-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="3d922-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3d922-111">Component</span></span>    |                            <span data-ttu-id="3d922-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="3d922-112">N\A</span></span>                             |
|  <span data-ttu-id="3d922-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3d922-113">Symbolic Name</span></span>  |                   <span data-ttu-id="3d922-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="3d922-114">SSO_ERROR_LOADLIBRARY</span></span>                    |
|  <span data-ttu-id="3d922-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3d922-115">Message Text</span></span>   |      <span data-ttu-id="3d922-116">%1 を読み込めませんでした %r</span><span class="sxs-lookup"><span data-stu-id="3d922-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="3d922-117">エラー コード: %2。</span><span class="sxs-lookup"><span data-stu-id="3d922-117">Error code: %2.</span></span>       |

## <a name="explanation"></a><span data-ttu-id="3d922-118">説明</span><span class="sxs-lookup"><span data-stu-id="3d922-118">Explanation</span></span>  
 <span data-ttu-id="3d922-119">このエラー イベントは、SSO サーバー プロセスに指定されたダイナミック リンク ライブラリ (DLL) を読み込めなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3d922-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="3d922-120">セットアップが正常に完了していないこと、またはセットアップ後に、DLL が削除されたことが完了した DLL が SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオン、不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d922-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="3d922-121">DLL が存在する場合、DLL への正しいパスを解決する SSO サービスに問題があります。</span><span class="sxs-lookup"><span data-stu-id="3d922-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="3d922-122">さらに、DLL 自体が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d922-122">Additionally, the DLL itself could be corrupted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3d922-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3d922-123">User Action</span></span>  
 <span data-ttu-id="3d922-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d922-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="3d922-125">多くの障害のセットアップが疑われるをアンインストールして、製品を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d922-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  

- <span data-ttu-id="3d922-126">1 つの DLL が見つからないか壊れている場合、しようとして、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3d922-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="3d922-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="3d922-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="3d922-128">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="3d922-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
