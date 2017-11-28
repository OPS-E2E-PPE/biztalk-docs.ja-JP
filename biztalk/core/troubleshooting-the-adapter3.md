---
title: "トラブルシューティング、Adapter3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], connecting [Oracle databases]
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], troubleshooting
- Oracle databases, connecting [JD Edwards OneWorld adapters]
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15197bcdc84e813d31a8d5292f5559aca1f8ae01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="8b264-102">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8b264-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="8b264-103">このトピックでは、Microsoft BizTalk Adapter for JD Edwards OneWorld の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8b264-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a><span data-ttu-id="8b264-104">送信ポートおよび受信ポートのプロパティでワイルドカードを使用できない</span><span class="sxs-lookup"><span data-stu-id="8b264-104">Cannot use wildcards in send and receive port properties</span></span>  
 <span data-ttu-id="8b264-105">Adapter for JD Edwards One World では、以下のプロパティ フィールドでのワイルドカードの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8b264-105">Adapter for JD Edwards One World does not support using wildcards in the following property fields:</span></span>  
  
|<span data-ttu-id="8b264-106">送信ポートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8b264-106">Send Port Property</span></span>|<span data-ttu-id="8b264-107">受信ポートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8b264-107">Receive Port Property</span></span>|  
|------------------------|---------------------------|  
|<span data-ttu-id="8b264-108">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="8b264-108">Username</span></span>|<span data-ttu-id="8b264-109">イベント ファイル パス</span><span class="sxs-lookup"><span data-stu-id="8b264-109">Event File Path</span></span>|  
|<span data-ttu-id="8b264-110">JDE 環境</span><span class="sxs-lookup"><span data-stu-id="8b264-110">JDE Environment</span></span>|<span data-ttu-id="8b264-111">イベント ターゲット名のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="8b264-111">Event Target Name prefix</span></span>|  
|<span data-ttu-id="8b264-112">Host</span><span class="sxs-lookup"><span data-stu-id="8b264-112">Host</span></span>||  
|<span data-ttu-id="8b264-113">ポート</span><span class="sxs-lookup"><span data-stu-id="8b264-113">Port</span></span>||  
|<span data-ttu-id="8b264-114">Java_Home</span><span class="sxs-lookup"><span data-stu-id="8b264-114">Java_Home</span></span>||  
|<span data-ttu-id="8b264-115">JDE JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="8b264-115">JDE JAR Files</span></span>||  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="8b264-116">Oracle データベースへの接続</span><span class="sxs-lookup"><span data-stu-id="8b264-116">Connecting to Oracle database</span></span>  
 <span data-ttu-id="8b264-117">Oracle データベースを JD Edwards で使用する場合、jdeinterop.ini ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b264-117">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="8b264-118">シングル サインオンを使用する場合、[JDBj-ORACLE] セクションは Oracle の tnsnames の場所を定義します。このデータベース パラメーターを使用する必要があります。また、SQLNET.ORA ファイルが BizTalk Server コンピューター上に存在する必要があります (このファイルは Oracle Client に付属しています)。</span><span class="sxs-lookup"><span data-stu-id="8b264-118">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="8b264-119">次の内容を jdeinterop.ini ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b264-119">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="8b264-120">[JDBj-ORACLE] の下に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b264-120">Under [JDBj-ORACLE], type:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="8b264-121">[JDBj-BOOTSTRAP DATA SOURCE] の下に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b264-121">Under [JDBj-BOOTSTRAP DATA SOURCE], type:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8b264-122">参照</span><span class="sxs-lookup"><span data-stu-id="8b264-122">See Also</span></span>  
 <span data-ttu-id="8b264-123">[JD Edwards OneWorld 用送信ポートを作成する方法](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="8b264-123">[How to Create Send Ports for JD Edwards OneWorld](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="8b264-124">JD Edwards OneWorld のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8b264-124">Troubleshooting JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)