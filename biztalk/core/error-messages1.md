---
title: "エラー Messages1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a><span data-ttu-id="4b724-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="4b724-102">Error Messages</span></span>
<span data-ttu-id="4b724-103">次の表に、JD Edwards EnterpriseOne システムのエラー メッセージおよび可能な対応策を示します。</span><span class="sxs-lookup"><span data-stu-id="4b724-103">The following table describes error messages in the JD Edwards EnterpriseOne system and provides possible corrections for them.</span></span>  
  
|<span data-ttu-id="4b724-104">エラー ID</span><span class="sxs-lookup"><span data-stu-id="4b724-104">Error ID</span></span>|<span data-ttu-id="4b724-105">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="4b724-105">Possible Cause / Error Description</span></span>|<span data-ttu-id="4b724-106">考えられる修正</span><span class="sxs-lookup"><span data-stu-id="4b724-106">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="4b724-107">E-JDE0027</span><span class="sxs-lookup"><span data-stu-id="4b724-107">E-JDE0027</span></span>|<span data-ttu-id="4b724-108">JD Edwards EnterpriseOne JAR ファイルが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="4b724-108">JD Edwards EnterpriseOne JAR files missing.</span></span> <span data-ttu-id="4b724-109">JD Edwards EnterpriseOne 接続オブジェクトを取得できません。</span><span class="sxs-lookup"><span data-stu-id="4b724-109">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span>|<span data-ttu-id="4b724-110">資格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b724-110">Verify your credentials.</span></span> <span data-ttu-id="4b724-111">CLASSPATH 設定およびログオン資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="4b724-111">Verify your CLASSPATH settings and logon credentials.</span></span> <span data-ttu-id="4b724-112">環境変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b724-112">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="4b724-113">I-JDE0043</span><span class="sxs-lookup"><span data-stu-id="4b724-113">I-JDE0043</span></span>|<span data-ttu-id="4b724-114">アプリケーション サーバー、ポート、環境、構成ファイルのパス、ユーザー、パスワードが間違っています。</span><span class="sxs-lookup"><span data-stu-id="4b724-114">Wrong App Server, Port, Environment, Path for Configuration File, User, Password.</span></span> <span data-ttu-id="4b724-115">ログインに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4b724-115">Log in failed.</span></span>|<span data-ttu-id="4b724-116">ログイン資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="4b724-116">Verify your log in credentials.</span></span> <span data-ttu-id="4b724-117">環境変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b724-117">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="4b724-118">I-JDE0048</span><span class="sxs-lookup"><span data-stu-id="4b724-118">I-JDE0048</span></span>|<span data-ttu-id="4b724-119">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne が開いているときに、jdearglist.txt ファイルが存在しないか、または空の場合、ログに情報メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b724-119">If the jdearglist.txt file does not exist or is empty, an informational message appears in the log when Microsoft BizTalk Adapter for JD Edwards EnterpriseOne opens.</span></span>|<span data-ttu-id="4b724-120">パラメーターの一覧を入力するには、自動的に右揃えになり左側に空白が埋め込まれるように、jdearglist.txt ファイルを更新してください。</span><span class="sxs-lookup"><span data-stu-id="4b724-120">Update the jdearglist.txt file to enter a list of parameters so that they are automatically right justified and padded on the left with blanks.</span></span> <span data-ttu-id="4b724-121">詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b724-121">For more information, see  [Handling String Values](../core/handling-string-values2.md).</span></span> <span data-ttu-id="4b724-122">jdearglist を変更するごとに、そのビジネス オブジェクトのスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b724-122">Every time you change the jdearglist, you must regenerate the schemas for that business object.</span></span>|  
|<span data-ttu-id="4b724-123">E-JDE0027</span><span class="sxs-lookup"><span data-stu-id="4b724-123">E-JDE0027</span></span>|<span data-ttu-id="4b724-124">JD Edwards EnterpriseOne 接続オブジェクトを取得できません。</span><span class="sxs-lookup"><span data-stu-id="4b724-124">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span> <span data-ttu-id="4b724-125">CLASSPATH および資格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b724-125">Please check your CLASSPATH and credentials.</span></span>|<span data-ttu-id="4b724-126">jdeinterop.ini の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="4b724-126">Verify the location of jdeinterop.ini.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b724-127">参照</span><span class="sxs-lookup"><span data-stu-id="4b724-127">See Also</span></span>  
 <span data-ttu-id="4b724-128">[JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="4b724-128">[Troubleshooting JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="4b724-129">テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="4b724-129">Technical Reference</span></span>](../core/technical-reference6.md)