---
title: "プロパティ エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d297db1a-352c-4e5a-b0aa-6edae8d74824
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c03358ba08df939e7058a6d73603969dcddd8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="properties-errors"></a><span data-ttu-id="0e887-102">プロパティ エラー</span><span class="sxs-lookup"><span data-stu-id="0e887-102">Properties Errors</span></span>
<span data-ttu-id="0e887-103">ここでは、WCF のプロパティ エラーを診断および解決するための詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e887-103">This section contains detailed information for diagnosing and resolving WCF Properties errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e887-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0e887-104">In This Section</span></span>  
  
-   [<span data-ttu-id="0e887-105">プロパティの読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="0e887-105">Error loading properties</span></span>](../core/error-loading-properties.md)  
  
-   [<span data-ttu-id="0e887-106">プロパティの保存エラー</span><span class="sxs-lookup"><span data-stu-id="0e887-106">Error saving properties</span></span>](../core/error-saving-properties.md)  
  
-   [<span data-ttu-id="0e887-107">無効なプロジェクトの場所</span><span class="sxs-lookup"><span data-stu-id="0e887-107">Invalid project location</span></span>](../core/invalid-project-location.md)  
  
-   [<span data-ttu-id="0e887-108">メッセージ部分の要素が見つかりません</span><span class="sxs-lookup"><span data-stu-id="0e887-108">Message part missing element</span></span>](../core/message-part-missing-element.md)  
  
-   [<span data-ttu-id="0e887-109">メッセージの種類の部分はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="0e887-109">Message types without parts are not supported</span></span>](../core/message-types-without-parts-are-not-supported.md)  
  
-   [<span data-ttu-id="0e887-110">OutboundCustomHeaders は正しい形式はいません</span><span class="sxs-lookup"><span data-stu-id="0e887-110">OutboundCustomHeaders does not have correct format</span></span>](../core/outboundcustomheaders-does-not-have-correct-format.md)  
  
-   [<span data-ttu-id="0e887-111">プロジェクトの場所が空ではありません。</span><span class="sxs-lookup"><span data-stu-id="0e887-111">The project location is not empty</span></span>](../core/the-project-location-is-not-empty.md)  
  
-   [<span data-ttu-id="0e887-112">XML 構成からエンドポイント動作の構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="0e887-112">Unable to create endpoint behavior configuration element from XML configuration</span></span>](../core/unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="0e887-113">XML 構成からサービス動作の構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="0e887-113">Unable to create service behavior configuration element from XML configuration</span></span>](../core/unable-to-create-service-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="0e887-114">クライアント エンドポイント構成をエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="0e887-114">Unable to export client endpoint configuration</span></span>](../core/unable-to-export-client-endpoint-configuration.md)  
  
-   [<span data-ttu-id="0e887-115">サービス エンドポイント構成をエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="0e887-115">Unable to export service endpoint configuration</span></span>](../core/unable-to-export-service-endpoint-configuration.md)  
  
-   [<span data-ttu-id="0e887-116">受信本文のパス式のコンテンツを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="0e887-116">Unable to find content for inbound body path expression</span></span>](../core/unable-to-find-content-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="0e887-117">受信本文のパス式に一致するものが見つかりません</span><span class="sxs-lookup"><span data-stu-id="0e887-117">Unable to find match for inbound body path expression</span></span>](../core/unable-to-find-match-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="0e887-118">予期しないルート要素</span><span class="sxs-lookup"><span data-stu-id="0e887-118">Unexpected root element</span></span>](../core/unexpected-root-element.md)  
  
-   [<span data-ttu-id="0e887-119">送信メッセージの認識できない型をマーシャ リング</span><span class="sxs-lookup"><span data-stu-id="0e887-119">Unrecognized outbound message marshalling type</span></span>](../core/unrecognized-outbound-message-marshalling-type.md)  
  
-   [<span data-ttu-id="0e887-120">サポートされていないセキュリティ アルゴリズム スイート</span><span class="sxs-lookup"><span data-stu-id="0e887-120">Unsupported security algorithm suite</span></span>](../core/unsupported-security-algorithm-suite.md)  
  
-   [<span data-ttu-id="0e887-121">サポートされていないトランザクション プロトコル</span><span class="sxs-lookup"><span data-stu-id="0e887-121">Unsupported transaction protocol</span></span>](../core/unsupported-transaction-protocol.md)  
  
-   [<span data-ttu-id="0e887-122">WCF クライアントでのシングル サインオンを使用するための偽装を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e887-122">WCF client must allow impersonation to use Single Sign-On</span></span>](../core/wcf-client-must-allow-impersonation-to-use-single-sign-on.md)  
  
-   [<span data-ttu-id="0e887-123">Windows コンポーネントがインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e887-123">Windows components may not be installed</span></span>](../core/windows-components-may-not-be-installed.md)