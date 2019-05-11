---
title: エラー Messages1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98c6c3f8e6b4e648d8f40add23ec45bb3821579f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347394"
---
# <a name="error-messages"></a><span data-ttu-id="a16d2-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="a16d2-102">Error Messages</span></span>
<span data-ttu-id="a16d2-103">次の表では、JD Edwards EnterpriseOne システムのエラー メッセージについて説明し、それらの考えられる修正方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-103">The following table describes error messages in the JD Edwards EnterpriseOne system and provides possible corrections for them.</span></span>  
  
|<span data-ttu-id="a16d2-104">エラー ID</span><span class="sxs-lookup"><span data-stu-id="a16d2-104">Error ID</span></span>|<span data-ttu-id="a16d2-105">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="a16d2-105">Possible Cause / Error Description</span></span>|<span data-ttu-id="a16d2-106">考えられる修正</span><span class="sxs-lookup"><span data-stu-id="a16d2-106">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="a16d2-107">E-JDE0027</span><span class="sxs-lookup"><span data-stu-id="a16d2-107">E-JDE0027</span></span>|<span data-ttu-id="a16d2-108">JD Edwards EnterpriseOne JAR ファイルがありません。</span><span class="sxs-lookup"><span data-stu-id="a16d2-108">JD Edwards EnterpriseOne JAR files missing.</span></span> <span data-ttu-id="a16d2-109">JD Edwards EnterpriseOne 接続オブジェクトを取得できません。</span><span class="sxs-lookup"><span data-stu-id="a16d2-109">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span>|<span data-ttu-id="a16d2-110">資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-110">Verify your credentials.</span></span> <span data-ttu-id="a16d2-111">CLASSPATH 設定およびログオン資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-111">Verify your CLASSPATH settings and logon credentials.</span></span> <span data-ttu-id="a16d2-112">環境変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a16d2-112">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="a16d2-113">JDE0043</span><span class="sxs-lookup"><span data-stu-id="a16d2-113">I-JDE0043</span></span>|<span data-ttu-id="a16d2-114">構成ファイル、ユーザー、パスワードをアプリ サーバー、ポート、環境、パスが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="a16d2-114">Wrong App Server, Port, Environment, Path for Configuration File, User, Password.</span></span> <span data-ttu-id="a16d2-115">ログインに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a16d2-115">Log in failed.</span></span>|<span data-ttu-id="a16d2-116">ログイン資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-116">Verify your log in credentials.</span></span> <span data-ttu-id="a16d2-117">環境変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a16d2-117">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="a16d2-118">JDE0048</span><span class="sxs-lookup"><span data-stu-id="a16d2-118">I-JDE0048</span></span>|<span data-ttu-id="a16d2-119">Jdearglist.txt ファイルが存在しないか、空では場合、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を開いたときにログに情報メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a16d2-119">If the jdearglist.txt file does not exist or is empty, an informational message appears in the log when Microsoft BizTalk Adapter for JD Edwards EnterpriseOne opens.</span></span>|<span data-ttu-id="a16d2-120">右揃えで配置して、左に空白が埋め込まれて自動的には、パラメーターの一覧を入力する、jdearglist.txt ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-120">Update the jdearglist.txt file to enter a list of parameters so that they are automatically right justified and padded on the left with blanks.</span></span> <span data-ttu-id="a16d2-121">詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-121">For more information, see  [Handling String Values](../core/handling-string-values2.md).</span></span> <span data-ttu-id="a16d2-122">Jdearglist を変更するたびに、そのビジネス オブジェクトのスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16d2-122">Every time you change the jdearglist, you must regenerate the schemas for that business object.</span></span>|  
|<span data-ttu-id="a16d2-123">E-JDE0027</span><span class="sxs-lookup"><span data-stu-id="a16d2-123">E-JDE0027</span></span>|<span data-ttu-id="a16d2-124">JD Edwards EnterpriseOne 接続オブジェクトを取得できません。</span><span class="sxs-lookup"><span data-stu-id="a16d2-124">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span> <span data-ttu-id="a16d2-125">CLASSPATH および資格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a16d2-125">Please check your CLASSPATH and credentials.</span></span>|<span data-ttu-id="a16d2-126">Jdeinterop.ini の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="a16d2-126">Verify the location of jdeinterop.ini.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a16d2-127">参照</span><span class="sxs-lookup"><span data-stu-id="a16d2-127">See Also</span></span>  
 <span data-ttu-id="a16d2-128">[JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="a16d2-128">[Troubleshooting JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="a16d2-129">テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="a16d2-129">Technical Reference</span></span>](../core/technical-reference6.md)