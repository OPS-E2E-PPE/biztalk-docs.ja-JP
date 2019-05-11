---
title: 認証エラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36524da9-da91-41e7-bf73-7781cde20c80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cec15641b3ada42c3562deb421e3591dde2bd699
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531233"
---
# <a name="there-was-an-authentication-failure"></a><span data-ttu-id="b03b5-102">認証エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="b03b5-102">There was an authentication failure</span></span>
## <a name="details"></a><span data-ttu-id="b03b5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b03b5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b03b5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b03b5-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| <span data-ttu-id="b03b5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b03b5-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    <span data-ttu-id="b03b5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b03b5-106">Event ID</span></span>     |                                                                                                 -                                                                                                 |
|  <span data-ttu-id="b03b5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b03b5-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b03b5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b03b5-108">EDI</span></span>                                                       |
|    <span data-ttu-id="b03b5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b03b5-109">Component</span></span>    |                                                                                            <span data-ttu-id="b03b5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b03b5-110">EDI Engine</span></span>                                                                                             |
|  <span data-ttu-id="b03b5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b03b5-111">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="b03b5-112">DescPartyNotFound</span><span class="sxs-lookup"><span data-stu-id="b03b5-112">DescPartyNotFound</span></span>                                                                                         |
|  <span data-ttu-id="b03b5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b03b5-113">Message Text</span></span>   | <span data-ttu-id="b03b5-114">認証エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b03b5-114">There was an authentication failure.</span></span> <span data-ttu-id="b03b5-115">処理中のメッセージに一致するパーティが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b03b5-115">Make sure that a matching party exists for the message being processed.</span></span> <span data-ttu-id="b03b5-116">存在する場合、メッセージ内のセキュリティ/パスワード情報がパーティの構成と一致します。</span><span class="sxs-lookup"><span data-stu-id="b03b5-116">And the security/password information in the message matches the Party configuration</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b03b5-117">説明</span><span class="sxs-lookup"><span data-stu-id="b03b5-117">Explanation</span></span>  
 <span data-ttu-id="b03b5-118">このエラー/警告/情報イベントは、BizTalk Server がメッセージの送信者を認証できなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b03b5-118">This Error/Warning/Information event indicates that the receive pipeline was unable to process the incoming interchange because BizTalk Server was unable to authenticate the sender of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b03b5-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b03b5-119">User Action</span></span>  
 <span data-ttu-id="b03b5-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b03b5-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="b03b5-121">インターチェンジ ヘッダーの中の送信者の修飾子と識別子 (X12 の場合は ISA5 と ISA6、EDIFACT の場合は UNB2.1 と UNB2.2 の各フィールド) が、パーティのプロパティに含まれる送信者の修飾子と識別子 ([EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページで定義された) に一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b03b5-121">Verify that the sender qualifier and identifier in the interchange header (fields ISA5 and ISA6 for X12 or UNB2.1 and UNB2.2 for EDIFACT) match the sender qualifier and identifier in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>  
  
-   <span data-ttu-id="b03b5-122">インターチェンジのヘッダー中のセキュリティ/パスワード情報 (X12 の場合は ISA3 と ISA4、EDIFACT の場合は UNB6.1 と UNB6.2 の各フィールド) が、パーティのプロパティに含まれるセキュリティ/パスワード情報 ([EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページで定義された) に一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b03b5-122">Verify that the security/password information in the header of the interchange (fields ISA3 and ISA4 for X12 or UNB6.1 and UNB6.2 for EDIFACT) match the security/password information in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>