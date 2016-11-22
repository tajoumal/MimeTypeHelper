package com.aprivacy.vault.android.common.mimetypes;

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.List;

import static java.util.Arrays.asList;

/**
 * Created by tajoumal on 04-Nov-16.
 */

public class MimeTypeHelper {

    // all the file types to be put into one list
    public static List<FileMimeType> types;

    public MimeTypeHelper() {
        types = asList(
                PDF, WORD, EXCEL, JPEG, ZIP, RAR, RTF, PNG, PPT, GIF, DLL_EXE, MSDOC,
                BMP, DLL_EXE, ZIP_7z, ZIP_7z_2, GZ_TGZ, TAR_ZH, TAR_ZV, OGG, ICO, XML, MIDI, FLV, WAVE, DWG, LIB_COFF, PST, PSD,
                AES, SKR, SKR_2, PKR, EML_FROM, ELF, TXT_UTF8, TXT_UTF16_BE, TXT_UTF16_LE, TXT_UTF32_BE, TXT_UTF32_LE
        );
    }


    // file headers are taken from here:
    //http://www.garykessler.net/library/file_sigs.html
    //mime types are taken from here:
    //http://www.webmaster-toolkit.com/mime-types.shtml

    // office and documents
    byte[] bytes = {69, 121, 101, 45, 62, 118, 101, 114, (byte) 196, (byte) 195, 61, 101, 98};

    public static final FileMimeType WORD = new FileMimeType(new byte[]{(byte) 0xEC, (byte) 0xA5, (byte) 0xC1, (byte) 0x00}, 512, "doc", "application/msword");
    public static final FileMimeType EXCEL = new FileMimeType(new byte[]{(byte) 0x09, (byte) 0x08, (byte) 0x10, (byte) 0x00, (byte) 0x00, (byte) 0x06, (byte) 0x05, (byte) 0x00}, 512, "xls", "application/excel");
    public static final FileMimeType PPT = new FileMimeType(new byte[]{(byte) 0xFD, (byte) 0xFF, (byte) 0xFF, (byte) 0xFF, 0, (byte) 0x00, (byte) 0x00, (byte) 0x00}, 512, "ppt", "application/mspowerpoint");

    //ms office and openoffice docs (they're zip files: rename and enjoy!)
    //don't add them to the list, as they will be 'subtypes' of the ZIP type
    public static final FileMimeType WORDX = new FileMimeType(new byte[0], 512, "docx", "application/vnd.openxmlformats-officedocument.wordprocessingml.document");
    public static final FileMimeType EXCELX = new FileMimeType(new byte[0], 512, "xlsx", "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet");
    public static final FileMimeType ODT = new FileMimeType(new byte[0], 512, "odt", "application/vnd.oasis.opendocument.text");
    public static final FileMimeType ODS = new FileMimeType(new byte[0], 512, "ods", "application/vnd.oasis.opendocument.spreadsheet");

    // common documents
    public static final FileMimeType RTF = new FileMimeType(new byte[]{(byte) 0x7B, (byte) 0x5C, (byte) 0x72, (byte) 0x74, (byte) 0x66, (byte) 0x31}, "rtf", "application/rtf");
    public static final FileMimeType PDF = new FileMimeType(new byte[]{(byte) 0x25, (byte) 0x50, (byte) 0x44, (byte) 0x46}, "pdf", "application/pdf");
    //    public static final FileMimeType PDF = new FileMimeType(new byte[]{(byte) 0x25, (byte) 0x50, (byte) 0x44, (byte) 0x46}, "pdf", "application/pdf");
    public static final FileMimeType MSDOC = new FileMimeType(new byte[]{(byte) 0xD0, (byte) 0xCF, (byte) 0x11, (byte) 0xE0, (byte) 0xA1, (byte) 0xB1, (byte) 0x1A, (byte) 0xE1}, "", "application/octet-stream");
    //application/xml text/xml
    public static final FileMimeType XML = new FileMimeType(new byte[]{(byte) 0x72, (byte) 0x73, (byte) 0x69, (byte) 0x6F, (byte) 0x6E, (byte) 0x3D, (byte) 0x22, (byte) 0x31,
            (byte) 0x2E, (byte) 0x30, (byte) 0x22, (byte) 0x3F, (byte) 0x3E}, "xml,xul", "text/xml");

    //text files
    public static final FileMimeType TXT = new FileMimeType(new byte[0], "txt", "text/plain");
    public static final FileMimeType TXT_UTF8 = new FileMimeType(new byte[]{(byte) 0xEF, (byte) 0xBB, (byte) 0xBF}, "txt", "text/plain");
    public static final FileMimeType TXT_UTF16_BE = new FileMimeType(new byte[]{(byte) 0xFE, (byte) 0xFF}, "txt", "text/plain");
    public static final FileMimeType TXT_UTF16_LE = new FileMimeType(new byte[]{(byte) 0xFF, (byte) 0xFE}, "txt", "text/plain");
    public static final FileMimeType TXT_UTF32_BE = new FileMimeType(new byte[]{(byte) 0x00, (byte) 0x00, (byte) 0xFE, (byte) 0xFF}, "txt", "text/plain");
    public static final FileMimeType TXT_UTF32_LE = new FileMimeType(new byte[]{(byte) 0xFF, (byte) 0xFE, (byte) 0x00, (byte) 0x00}, "txt", "text/plain");


    // graphics
//    
//    region Graphics
//    jpeg,png,gif,bmp,ico

    public static final FileMimeType JPEG = new FileMimeType(new byte[]{(byte) 0xFF, (byte) 0xD8, (byte) 0xFF}, "jpg", "image/jpeg");
    public static final FileMimeType PNG = new FileMimeType(new byte[]{(byte) 0x89, (byte) 0x50, (byte) 0x4E, (byte) 0x47, (byte) 0x0D, (byte) 0x0A, (byte) 0x1A, (byte) 0x0A}, "png", "image/png");
//    public static final FileMimeType PNG = new FileMimeType(new byte[]{(byte) -77, (byte) 0x50, (byte) 0x4E, (byte) 0x47, (byte) 0x0D, (byte) 0x0A, (byte) 0x1A, (byte) 0x0A}, "jpg", "image/jpg");
//    public static final FileMimeType PNG = new FileMimeType(new byte[]{(byte) -0x77, (byte) 0x50, (byte) 78, (byte) 71, (byte) 13, (byte) 10, (byte) 26, (byte) 10}, "png", "image/png");
    public static final FileMimeType GIF = new FileMimeType(new byte[]{(byte) 0x47, (byte) 0x49, (byte) 0x46, (byte) 0x38, 0, (byte) 0x61}, "gif", "image/gif");
    public static final FileMimeType BMP = new FileMimeType(new byte[]{66, 77}, "bmp", "image/gif");
    public static final FileMimeType ICO = new FileMimeType(new byte[]{0, 0, 1, 0}, "ico", "image/x-icon");


    //bmp, tiff

//    region Zip, 7zip,rar,dll_exe,tar,bz2,gz_tgz

    public static final FileMimeType GZ_TGZ = new FileMimeType(new byte[]{(byte) 0x1F, (byte) 0x8B, (byte) 0x08}, "gz, tgz", "application/x-gz");

    public static final FileMimeType ZIP_7z = new FileMimeType(new byte[]{66, 77}, "7z", "application/x-compressed");
    public static final FileMimeType ZIP_7z_2 = new FileMimeType(new byte[]{(byte) 0x37, (byte) 0x7A, (byte) 0xBC, (byte) 0xAF, (byte) 0x27, (byte) 0x1C}, "7z", "application/x-compressed");

    public static final FileMimeType ZIP = new FileMimeType(new byte[]{(byte) 0x50, (byte) 0x4B, (byte) 0x03, (byte) 0x04}, "zip", "application/x-compressed");
    public static final FileMimeType RAR = new FileMimeType(new byte[]{(byte) 0x52, (byte) 0x61, (byte) 0x72, (byte) 0x21}, "rar", "application/x-compressed");
    public static final FileMimeType DLL_EXE = new FileMimeType(new byte[]{(byte) 0x4D, (byte) 0x5A}, "dll, exe", "application/octet-stream");

    //Compressed tape archive file using standard (Lempel-Ziv-Welch) compression
    public static final FileMimeType TAR_ZV = new FileMimeType(new byte[]{(byte) 0x1F, (byte) 0x9D}, "tar.z", "application/x-tar");

    //Compressed tape archive file using LZH (Lempel-Ziv-Huffman) compression
    public static final FileMimeType TAR_ZH = new FileMimeType(new byte[]{(byte) 0x1F, (byte) 0xA0}, "tar.z", "application/x-tar");

    //bzip2 compressed archive
    public static final FileMimeType BZ2 = new FileMimeType(new byte[]{(byte) 0x42, (byte) 0x5A, (byte) 0x68}, "bz2,tar,bz2,tbz2,tb2", "application/x-bzip2");


//    //#endregion
//
//
//    //#
//    region Media
//    ogg,midi,flv,dwg,pst,psd

    // media
    public static final FileMimeType OGG = new FileMimeType(new byte[]{103, 103, 83, 0, 2, 0, 0, 0, 0, 0, 0, 0, 0}, "oga,ogg,ogv,ogx", "application/ogg");
    //MID, MIDI	 	Musical Instrument Digital Interface (MIDI) sound file
    public static final FileMimeType MIDI = new FileMimeType(new byte[]{(byte) 0x4D, (byte) 0x54, (byte) 0x68, (byte) 0x64}, "midi,mid", "audio/midi");

    //FLV	 	Flash video file
    public static final FileMimeType FLV = new FileMimeType(new byte[]{(byte) 0x46, (byte) 0x4C, (byte) 0x56, (byte) 0x01}, "flv", "application/unknown");

    //WAV	 	Resource Interchange File Format -- Audio for Windows file, where xx xx xx xx is the file size (little endian), audio/wav audio/x-wav

    public static final FileMimeType WAVE = new FileMimeType(new byte[]{(byte) 0x52, (byte) 0x49, (byte) 0x46, (byte) 0x46, 0, 0, 0, 0,
            (byte) 0x57, (byte) 0x41, (byte) 0x56, (byte) 0x45, (byte) 0x66, (byte) 0x6D, (byte) 0x74, (byte) 0x20}, "wav", "audio/wav");

    public static final FileMimeType PST = new FileMimeType(new byte[]{(byte) 0x21, (byte) 0x42, (byte) 0x44, (byte) 0x4E}, "pst", "application/octet-stream");

    //eneric AutoCAD drawing image/vnd.dwg  image/x-dwg application/acad
    public static final FileMimeType DWG = new FileMimeType(new byte[]{(byte) 0x41, (byte) 0x43, (byte) 0x31, (byte) 0x30}, "dwg", "application/acad");

    //Photoshop image file
    public static final FileMimeType PSD = new FileMimeType(new byte[]{(byte) 0x38, (byte) 0x42, (byte) 0x50, (byte) 0x53}, "psd", "application/octet-stream");

//    //#endregion

    public static final FileMimeType LIB_COFF = new FileMimeType(new byte[]{(byte) 0x21, (byte) 0x3C, (byte) 0x61, (byte) 0x72, (byte) 0x63, (byte) 0x68, (byte) 0x3E, (byte) 0x0A}, "lib", "application/octet-stream");

//    //#
//    region Crypto
//    aes,skr,skr_2,pkr

    //AES Crypt file format. (The fourth byte is the version number.)
    public static final FileMimeType AES = new FileMimeType(new byte[]{(byte) 0x41, (byte) 0x45, (byte) 0x53}, "aes", "application/octet-stream");

    //SKR	 	PGP secret keyring file
    public static final FileMimeType SKR = new FileMimeType(new byte[]{(byte) 0x95, (byte) 0x00}, "skr", "application/octet-stream");

    //SKR	 	PGP secret keyring file
    public static final FileMimeType SKR_2 = new FileMimeType(new byte[]{(byte) 0x95, (byte) 0x01}, "skr", "application/octet-stream");

    //PKR	 	PGP public keyring file
    public static final FileMimeType PKR = new FileMimeType(new byte[]{(byte) 0x99, (byte) 0x01}, "pkr", "application/octet-stream");


//    //#endregion

    /*
     * 46 72 6F 6D 20 20 20 or	 	From
    46 72 6F 6D 20 3F 3F 3F or	 	From ???
    46 72 6F 6D 3A 20	 	From:
    EML	 	A commmon file extension for e-mail files. Signatures shown here
    are for Netscape, Eudora, and a generic signature, respectively.
    EML is also used by Outlook Express and QuickMail.
     */
    public static final FileMimeType EML_FROM = new FileMimeType(new byte[]{(byte) 0x46, (byte) 0x72, (byte) 0x6F, (byte) 0x6D}, "eml", "message/rfc822");


    //EVTX	 	Windows Vista event log file
    public static final FileMimeType ELF = new FileMimeType(new byte[]{(byte) 0x45, (byte) 0x6C, (byte) 0x66, (byte) 0x46, (byte) 0x69, (byte) 0x6C, (byte) 0x65, (byte) 0x00}, "elf", "text/plain");

    // number of bytes we read from a file
    public static int MaxHeaderSize = 560;  // some file formats have headers offset to 512 bytes


    public FileMimeType guessFileMimeType(final File file) {
        byte[] buffer = new byte[MaxHeaderSize];
        InputStream is = null;
        try {
            is = new FileInputStream(file);

            if (is.read(buffer) != buffer.length) {
                // do something

            }
            is.close();
        } catch (IOException e) {
            e.printStackTrace();
        }

        for (FileMimeType type : types) {
            if (contains(buffer, type.getHeader())) {
                return type;
            }
        }
        return null;
    }

    static boolean contains(byte[] arrays, byte[] other) {
        return indexOf(arrays, other) != -1;
    }

    public static int indexOf(byte[] data, byte[] pattern) {
        int[] failure = computeFailure(pattern);

        int j = 0;

        for (int i = 0; i < data.length; i++) {
            while (j > 0 && pattern[j] != data[i]) {
                j = failure[j - 1];
            }
            if (pattern[j] == data[i]) {
                j++;
            }
            if (j == pattern.length) {
                return i - pattern.length + 1;
            }
        }
        return -1;
    }

    /**
     * Computes the failure function using a boot-strapping process,
     * where the pattern is matched against itself.
     */
    private static int[] computeFailure(byte[] pattern) {
        int[] failure = new int[pattern.length];

        int j = 0;
        for (int i = 1; i < pattern.length; i++) {
            while (j>0 && pattern[j] != pattern[i]) {
                j = failure[j - 1];
            }
            if (pattern[j] == pattern[i]) {
                j++;
            }
            failure[i] = j;
        }

        return failure;
    }
}
