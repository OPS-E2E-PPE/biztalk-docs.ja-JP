---
title: ファイル アダプタ プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e1c6860b002b41555337a0bf7e8cb931f2c2bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245994"
---
# <a name="file-adapter-property-schema-and-properties"></a><span data-ttu-id="8b65b-102">ファイル アダプタ プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="8b65b-102">File adapter property schema and properties</span></span>
<span data-ttu-id="8b65b-103">ファイル アダプタ プロパティ スキーマのプロパティを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-103">The following table contains the properties in the File adapter property schema.</span></span>  
  
 <span data-ttu-id="8b65b-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span><span class="sxs-lookup"><span data-stu-id="8b65b-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span></span>  
  
|<span data-ttu-id="8b65b-105">名前</span><span class="sxs-lookup"><span data-stu-id="8b65b-105">Name</span></span>|<span data-ttu-id="8b65b-106">型</span><span class="sxs-lookup"><span data-stu-id="8b65b-106">Type</span></span>|<span data-ttu-id="8b65b-107">Description</span><span class="sxs-lookup"><span data-stu-id="8b65b-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="8b65b-108">**CopyMode**</span><span class="sxs-lookup"><span data-stu-id="8b65b-108">**CopyMode**</span></span>|<span data-ttu-id="8b65b-109">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8b65b-109">xs:unsignedInt</span></span>|<span data-ttu-id="8b65b-110">ファイルにメッセージを書き込む際に使用するコピー モードを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-110">Defines the copy mode to use when writing a message to a file.</span></span> <span data-ttu-id="8b65b-111">有効な値は、</span><span class="sxs-lookup"><span data-stu-id="8b65b-111">Valid values are:</span></span><br /><br /> <span data-ttu-id="8b65b-112">**(0) を追加します。**</span><span class="sxs-lookup"><span data-stu-id="8b65b-112">**Append (0).**</span></span> <span data-ttu-id="8b65b-113">ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの末尾にメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-113">The File send handler opens a file if it exists and appends a message to the end of the file.</span></span> <span data-ttu-id="8b65b-114">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-114">If the file does not exist, the File send handler creates a new file.</span></span><br /><br /> <span data-ttu-id="8b65b-115">**新しい (1) を作成します。**</span><span class="sxs-lookup"><span data-stu-id="8b65b-115">**Create new (1).**</span></span> <span data-ttu-id="8b65b-116">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成し、そのファイルにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8b65b-116">If a file does not exist, the File send handler creates a new file and writes to it.</span></span> <span data-ttu-id="8b65b-117">ファイルが存在する場合は、ファイル送信ハンドラがエラーを報告し、送信ポートの通常のアダプタ再試行ロジックに従ってメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-117">If the file already exists, the File send handler reports an error and then follows common adapter retry logic for send ports.</span></span> <span data-ttu-id="8b65b-118">これはファイル送信ハンドラの既定のコピー モードです。</span><span class="sxs-lookup"><span data-stu-id="8b65b-118">This is a default copy mode for the File send handler.</span></span><br /><br /> <span data-ttu-id="8b65b-119">**(2) を上書きします。**</span><span class="sxs-lookup"><span data-stu-id="8b65b-119">**Overwrite (2).**</span></span> <span data-ttu-id="8b65b-120">ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの内容を上書きします。</span><span class="sxs-lookup"><span data-stu-id="8b65b-120">The File send handler opens a file if it exists and overwrites its content.</span></span> <span data-ttu-id="8b65b-121">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-121">If the file does not exist, the File send handler creates a new file.</span></span>|  
|<span data-ttu-id="8b65b-122">**AllowCacheOnWrite**</span><span class="sxs-lookup"><span data-stu-id="8b65b-122">**AllowCacheOnWrite**</span></span>|<span data-ttu-id="8b65b-123">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="8b65b-123">xs:Boolean</span></span>|<span data-ttu-id="8b65b-124">ファイルにメッセージを書き込む際にファイル アダプタでファイル システム キャッシュを使用するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-124">Defines whether the File adapter uses file system caching when writing messages to a file.</span></span>|  
|<span data-ttu-id="8b65b-125">**ReceivedFileName**</span><span class="sxs-lookup"><span data-stu-id="8b65b-125">**ReceivedFileName**</span></span>|<span data-ttu-id="8b65b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b65b-126">xs:string</span></span>|<span data-ttu-id="8b65b-127">ファイル アダプタがメッセージを読み取るファイルの完全な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-127">Defines the full name of the file from which the File adapter reads the message.</span></span>|  
|<span data-ttu-id="8b65b-128">**FileCreationTime**</span><span class="sxs-lookup"><span data-stu-id="8b65b-128">**FileCreationTime**</span></span>|<span data-ttu-id="8b65b-129">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="8b65b-129">xs:datetime</span></span>|<span data-ttu-id="8b65b-130">ファイル受信アダプタで監視されているフォルダにファイルが書き込まれた時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-130">Defines the time that the file was written to the folder that is monitored by the File receive adapter.</span></span>|  
|<span data-ttu-id="8b65b-131">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="8b65b-131">**Username**</span></span>|<span data-ttu-id="8b65b-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b65b-132">xs:string</span></span>|<span data-ttu-id="8b65b-133">ネットワーク共有にアクセスするために指定した代替資格情報で使用したアカウントのユーザー名を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-133">Defines the user name for the account used when specifying alternative credentials to access a network share.</span></span>|  
|<span data-ttu-id="8b65b-134">**Password**</span><span class="sxs-lookup"><span data-stu-id="8b65b-134">**Password**</span></span>|<span data-ttu-id="8b65b-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b65b-135">xs:string</span></span>|<span data-ttu-id="8b65b-136">ネットワーク共有にアクセスするために指定した代替資格情報で使用したアカウントのパスワードを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-136">Defines the password for the account used when specifying alternative credentials to access a network share.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b65b-137">参照</span><span class="sxs-lookup"><span data-stu-id="8b65b-137">See Also</span></span>  
 [<span data-ttu-id="8b65b-138">ファイル アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="8b65b-138">Configuring the File Adapter</span></span>](../core/configure-the-file-adapter.md)